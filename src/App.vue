<template>
  <FormularioCita @agregar-cita="recibirCita"/>
  <InfoCita/>
  
  <p v-if="citas.length == 0">Aún no hay consultas registradas</p>
  <p v-else>Algo</p>
</template>

<script>
import FormularioCita from './components/FormularioCita.vue'
import InfoCita from './components/InfoCita.vue'

export default {
  name: 'App',
  data(){
    return{
      citas: [],

    }
  },
  components: {
    FormularioCita,
    InfoCita
  },

  methods:{
    recibirCita(citaRecibida){
      console.log("ᓀ‸ᓂ");
      console.log(citaRecibida);
      this.citas.push(citaRecibida);
    }
  },
}
</script>

<style>

</style>
