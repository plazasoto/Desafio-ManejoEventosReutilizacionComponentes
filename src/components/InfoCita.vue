<template>
    <div class="card" 
    :class="{
        baja: Gravedad == 'baja',
        media: Gravedad == 'media',
        alta: Gravedad == 'alta'
    }">
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
            "Motivo",
            "Gravedad"
        ],
        methods:{

        },
    }
</script>

<style scoped>
    .card{
        display: inline-block;
        text-align: center;
        width: 15%;
        border-radius: 10px;
        padding: 5px 50px;
        margin: 5px;
    }

    .baja{
        color: black;
        background-color: limegreen;
    }
    .media{
        color: black;
        background-color: yellow;
    } 
    .alta{
        color: white;
        background-color: red;
    } 
</style>