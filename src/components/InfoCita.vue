<template>
    <div class="card">
        <!-- <div v-for="(value, key) in cita" :key="value">
            <h4>{{ key }}</h4>
            <p>{{ value }}</p>
        </div> -->
        <h4>Paciente</h4>
        <p>{{ Paciente }}</p>
        <h4>Fecha</h4>
        <p>{{ Fecha }}</p>
        <h4>Hora</h4>
        <p>{{ Hora }}</p>
        <h4>Motivo</h4>
        <p>{{ Motivo }}</p>
        <button>Eliminar</button>
    </div>
</template>

<script>
    export default{
        /* data(){
            return{
                cita:{
                    Paciente:"",
                    Fecha:"",
                    Hora:"",
                    Motivo:"",
                },
            }  
        }, */
        props: [
            "Paciente",
            "Fecha",
            "Hora",
            "Motivo"
        ],
    }
</script>

<style scoped>
    .card{
        display: inline-block;
        width: max-content;
        border: 1px solid;
        border-radius: 10px;
        padding: 5px 50px;
        margin: 5px;
    }
</style>