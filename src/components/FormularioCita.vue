<template>
    <form @submit.prevent="">
        <div>
            <label for="paciente" :class="{ rojo : !cita.paciente }">Paciente</label>
            <br>
            <input type="text" id="paciente" v-model="cita.paciente">
        </div>
        <div>
            <label for="fecha"  :class="{ rojo : !cita.fecha }">Fecha</label>
            <br>
            <input type="date" id="fecha" v-model="cita.fecha">
        </div>
        <div>
            <label for="hora" :class="{ rojo : !cita.hora }">Hora</label>
            <br>
            <input type="time" id="hora" v-model="cita.hora">
        </div>
        <div>
            <label for="gravedad" :class="{ rojo : !cita.gravedad }">Gravedad</label>
            <br>
            <select name="gravedad" id="gravedad" v-model="cita.gravedad">
                <option value="baja">Baja</option>
                <option value="media">Media</option>
                <option value="alta">Alta</option>
            </select>
        </div>
        <div>
            <label for="motivo" :class="{ rojo : !cita.motivo }">Motivo</label>
            <br>
            <input type="text" id="motivo" v-model="cita.motivo" @change="habilitarBoton()">
        </div>
        <br>
        <button :disabled="botonDeshabilitado" >Agregar</button>
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
                    gravedad: "",
                    motivo: "",
                },
                botonDeshabilitado: true,
            }
        },
        methods:{
            habilitarBoton(){// meh 
                if(
                    this.cita.paciente &&
                    this.cita.fecha &&
                    this.cita.hora &&
                    this.cita.gravedad &&
                    this.cita.motivo
                    ){
                    this.botonDeshabilitado = false;
                }else{
                    this.botonDeshabilitado = true;
                }
            },
        }
    };
</script>

<style scoped>
    form{
        border: 2px solid black;
        border-radius: 10px;
        padding: 5px;
    }

    .rojo{
        color: red;
    }
</style>