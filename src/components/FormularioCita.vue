<template>
    <form @submit.prevent="">
        <div>
            <label for="paciente">Paciente</label>
            <br>
            <input type="text" id="paciente" v-model="cita.paciente">
        </div>
        <div>
            <label for="fecha">Fecha</label>
            <br>
            <input type="date" id="fecha" v-model="cita.fecha">
        </div>
        <div>
            <label for="hora">Hora</label>
            <br>
            <input type="time" id="hora" v-model="cita.hora">
        </div>
        <div>
            <label for="gravedad">Gravedad</label>
            <br>
            <select name="gravedad" id="gravedad" v-model="cita.gravedad">
                <option value="baja">Baja</option>
                <option value="media">Media</option>
                <option value="alta">Alta</option>
            </select>
        </div>
        <div>
            <label for="motivo">Motivo</label>
            <br>
            <input type="text" id="motivo" v-model="cita.motivo">
        </div>
        <br>
        <button>Agregar</button>
    </form>
</template>

<script>
    export default{
        data(){
            return{
                cita:{
                    paciente: "",
                    fecha: "",
                    hora: "",
                    gravedad: "baja",
                    motivo: "",
                }
            }
        },
        methods:{
            
        }
    };
</script>

<style scoped>
    form{
        border: 2px solid black;
        border-radius: 10px;
        padding: 5px;
    }
</style>