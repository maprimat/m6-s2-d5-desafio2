<!-- HTML Base -->
<template>
    <div id="app">
        <h1>Registro de tarjeta de crédito</h1>

        <CardTarjeta />

    </div>
</template>

<!-- Logica -->
<script>
import CardTarjeta from "./components/CardTarjeta.vue"
export default {
    name: 'App',
    components: {
        CardTarjeta
    }
}
</script>

<!-- Estilos -->
<style>
h1 {
    text-align: center;
}
</style>