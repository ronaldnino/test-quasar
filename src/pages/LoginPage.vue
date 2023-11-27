<template>
  <q-card class="q-ma-xl">
   <div class="row">
    <div class="col-0 col-sm-5 bg-primary rounded-left-borders xs-hide">
     <div class="row full-width q-px-xl q-pb-xl full-height flex flex-center">
      <div class="">
        <img
          alt="Identidad"
          src="~assets/identidad.png"
          style="width: 200px; height: 200px"
        >
      </div>
     </div>
    </div>

    <div class="col-12 col-sm-7">
     <div class="row q-ml-sm q-mt-sm sm-and-up-hide">
      <div class="col-12 fredoka text-subtitle1">
       <router-link class="text-primary" style="text-decoration: none" to="/">

       </router-link>
      </div>
     </div>
     <div class="row q-pa-sm-sm q-pa-md">
      <div class="col-12">
       <q-card-section>
        <div class="q-mb-xl">
         <div class="flex justify-center">
          <div class="text-h4 text-uppercase q-my-none text-weight-bold text-primary fredoka">
           Obtener Token
          </div>
         </div>
        </div>

        <q-form ref="form" class="q-gutter-md" @submit="submit">

         <div>
          <q-btn class="full-width fredoka" color="primary" label="Obtener Token" rounded
           type="submit"></q-btn>
         </div>
         <div>
         </div>
        </q-form>
       </q-card-section>
      </div>
     </div>
    </div>
   </div>
  </q-card>
 </template>




<script>
export default {
  methods: {
    submit() {
      console.log("dsasds")
      var data = {
    'user': 'val1',
    'pass': 'val2'
}
      this.$api.post('rest/api/1.0/consultas-genericas/token', data)
        .then(response => {
          console.log(response.data);
        })
        .catch(error => {
          console.error('Error fetching data:', error);
        });
    },
  },
};

</script>
