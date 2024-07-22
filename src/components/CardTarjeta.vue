<!-- HTML Base -->
<template>
    <div class="contenedorTarjeta">
        <form>
            <div>
                <label>Título de la tarjeta: </label>
                <!-- Atributo v-model unidireccional -->
                <input v-model="tituloTarjeta" />
            </div>

            <div>
                <label>Chip SRC: </label>
                <!-- Atributo v-model unidireccional -->
                <input v-model="chipTarjeta" disabled/>
            </div>

            <div>
                <label>Número: </label>
                <!-- Atributo v-model unidireccional -->
                <input maxlength="19" v-model="numeroTarjeta"/>
            </div>

            <div>
                <label>Fecha de expiración: </label>
                <!-- Atributo v-model unidireccional -->
                <input v-model="fechaExpiracion"/>
            </div>

            <div>
                <label>Propietario: </label>
                <!-- Atributo v-model unidireccional -->
                <input v-model="propietarioTarjeta"/>
            </div>

            <div>
                <label>Tipo de tarjeta SRC: </label>
                <!-- Atributo v-model unidireccional -->
                <input v-model="tipoTarjeta" disabled/>
            </div>
        </form>

        <div class="tarjeta">
            <h3>{{ tituloTarjeta }}</h3>
            <!-- Binding unidireccional, atributo src a variable -->
            <img width="40" :src="chipTarjeta" alt="Imagen chip" />
            <div>
                <h2>{{ numeroTarjeta }}</h2>
                <span>Fecha Exp: <b>{{ fechaExpiracion}}</b></span>
            </div>
            <footer>
                <span>{{ propietarioTarjeta}}</span>
                <!-- Binding unidireccional, atributo src a variable -->
                <img width="60" :src="tipoTarjeta" alt="Imagen tipo de tarjeta"/>
            </footer>
        </div>
    </div>
</template>

<!-- Logica -->
<script>
//Export de componente CardTarjeta para usar en App.vue
export default {
    // Nombre de componente
    name: "CardTarjeta",
    // Data a usar en el componente
    data() {
        // Variables para los inputs
        return {
            tituloTarjeta: "Visa Classic Crédito",
            chipTarjeta: "/img/chip.png",
            numeroTarjeta: "400 500 600 700",
            fechaExpiracion: "01/30",
            propietarioTarjeta: "William Henry Gates III",
            tipoTarjeta: "/img/visa.png"
        };
    },
};
</script>

<!-- Estilos -->
<style scoped>
* {
    margin: 0;
}

.contenedorTarjeta {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 60vh;
    font-size: 10px;
    font-family: sans-serif;
    gap: 40px;
}

form {
    padding: 18px;
    border-radius: 20px;
    border: ridge 1px;
    box-shadow: 1px 1px 1px 1px gray;
    font-weight: bold;
    display: flex;
    flex-direction: column;
    gap: 15px;
    justify-content: center;
}

form div {
    display: grid;
    grid-template-columns: 100px 200px;
    align-items: center;
    gap: 5px;
}

form div label {
    text-align: right;
}

.tarjeta {
    width: 400px;
    height: 230px;
    background: #1c1a1e;
    color: white;
    border-radius: 20px;
    padding: 20px;
    box-shadow: 0px 0px 10px 2px black;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

h3 {
    font-size: 20px;
}

h2 {
    font-size: 30px;
    letter-spacing: 10px;
    margin-bottom: 15px;
    text-shadow: 0px 0px 1px gold;
    font-family: Times;
}

b {
    font-size: 16px;
}

footer {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    font-weight: bold;
    font-size: 18px;
    text-transform: uppercase;
    font-style: italic;
}
</style>