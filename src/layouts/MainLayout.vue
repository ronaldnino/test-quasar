<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>

        </q-toolbar-title>

        <div>versión 0.7</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          Enlaces esenciales
        </q-item-label>
        <q-item
          clickable
          target="_blank"
          href="https://www.renap.gob.gt/"

        >
          <q-item-section
            avatar
          >
            <q-icon name="public" />
          </q-item-section>

          <q-item-section>
            <q-item-label>Sitio Web</q-item-label>
            <q-item-label caption>www.renap.gob.gt</q-item-label>
          </q-item-section>
        </q-item>

        <q-item
          clickable

          @click="navegar_login"
        >
          <q-item-section
            avatar
          >
            <q-icon name="no_encryption" />
          </q-item-section>

          <q-item-section>
            <q-item-label>Obtener Token</q-item-label>
            <q-item-label caption>renap.consultas-genericas.token</q-item-label>
          </q-item-section>
        </q-item>

        <q-item
          clickable

          @click="navegar_query"
        >
          <q-item-section
            avatar
          >
            <q-icon name="search" />
          </q-item-section>

          <q-item-section>
            <q-item-label>Consulta</q-item-label>
            <q-item-label caption>renap.consultas-genericas.busqueda</q-item-label>
          </q-item-section>
        </q-item>


      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import { useRouter } from "vue-router";


const router = useRouter();



export default defineComponent({
  name: 'MainLayout',

  components: {

  },

  setup () {
    const leftDrawerOpen = ref(false)
    const router = useRouter();
    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      },
      navegar_login () {
        router.push('/login');
      },
      navegar_query () {
        router.push('/query');
      },
      router
    }
  }
})
</script>
