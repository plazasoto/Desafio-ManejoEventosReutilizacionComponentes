<template>
  <FormularioCita @agregar-cita="recibirCita"/>

  <div id="citasAgendadas" v-for="cita in citas" :key="cita">
    <InfoCita 
    :Paciente="cita.paciente"
    :Fecha="cita.fecha"
    :Hora="cita.hora"
    :Motivo="cita.motivo"
    :Gravedad="cita.gravedad"
    />

  </div>
  
  <p v-if="citas.length == 0" id="sinRegistros">Aún no hay consultas registradas</p>
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
      /* console.log("ᓀ‸ᓂ");
      console.log(citaRecibida); */
      this.citas.push(citaRecibida);
    },
  },
}
</script>

<style>
#citasAgendadas{
  display: inline;
}

#sinRegistros{
  color: red;
  text-align: center;
}
</style>
