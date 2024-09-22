<template>
    <form @submit.prevent="" @input="habilitarBoton()">
        <div class="flex">

        
        <div class="inlineblock">
            <label for="paciente" :class="{ rojo : !cita.paciente }">Paciente</label>
            <br>
            <input type="text" id="paciente" v-model="cita.paciente">
        </div>
        <div class="inlineblock">
            <label for="fecha"  :class="{ rojo : !cita.fecha }">Fecha</label>
            <br>
            <input type="date" id="fecha" v-model="cita.fecha">
        </div>
        <div class="inlineblock">
            <label for="hora" :class="{ rojo : !cita.hora }">Hora</label>
            <br>
            <input type="time" id="hora" v-model="cita.hora">
        </div>
        <div class="inlineblock">
            <label for="gravedad" :class="{ rojo : !cita.gravedad }">Gravedad</label>
            <br>
            <select name="gravedad" id="gravedad" v-model="cita.gravedad" @change="habilitarBoton()">
                <option value="baja">Baja</option>
                <option value="media">Media</option>
                <option value="alta">Alta</option>
            </select>
        </div>
        <div class="inlineblock">
            <label for="motivo" :class="{ rojo : !cita.motivo }">Motivo</label>
            <br>
            <input type="text" id="motivo" v-model="cita.motivo" >
        </div>


        </div>
        <div class="flex">

            <button 
            :disabled="botonDeshabilitado" 
            @click="agregarCita" 
            :style="{ cursor: botonDeshabilitado ? 'not-allowed' : 'pointer'}" >
                Agregar
            </button>
        </div>
        
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
            habilitarBoton(){
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

            limpiarFormulario(){
                this.cita.paciente = "";
                this.cita.fecha = "";
                this.cita.hora = "";
                this.cita.gravedad = "";
                this.cita.motivo = "";
            },

            agregarCita(){
                //console.log(this.cita);
                this.$emit('agregar-cita', structuredClone(this.cita));
                this.limpiarFormulario();
                this.habilitarBoton();
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

    .flex{
        display:flex;
        justify-content: center;
    }

    .rojo{
        color: red;
    }

    .inlineblock{
        display: inline-block;
        text-align: center;
        margin: 5px;
    }
</style>