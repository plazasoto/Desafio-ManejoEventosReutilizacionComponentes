<template>
  <FormularioCita/>
  <InfoCita/>
</template>

<script>
import FormularioCita from './components/FormularioCita.vue'
import InfoCita from './components/InfoCita.vue'

export default {
  name: 'App',
  data(){
    return{
      componenteARenderizar: "e",
    }
  },
  components: {
    FormularioCita,
    InfoCita
  },
}
</script>

<style>

</style>
