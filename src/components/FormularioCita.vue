<template>
    <form>
        <div>
            <label for="paciente">Paciente</label>
            <br>
            <input type="text" id="paciente">
        </div>
        <div>
            <label for="fecha">Fecha</label>
            <br>
            <input type="date" id="fecha">
        </div>
        <div>
            <label for="hora">Hora</label>
            <br>
            <input type="time" id="hora">
        </div>
        <div>
            <label for="gravedad">Gravedad</label>
            <br>
            <select name="gravedad" id="gravedad">
                <option value="baja">Baja</option>
                <option value="media">Media</option>
                <option value="alta">Alta</option>
            </select>
        </div>
        <div>
            <label for="motivo">Motivo</label>
            <br>
            <input type="text" id="motivo">
        </div>
        <br>
        <button>Agregar</button>
    </form>
</template>

<style scoped>
    form{
        border: 2px solid black;
        border-radius: 10px;
        padding: 5px;
    }
</style>