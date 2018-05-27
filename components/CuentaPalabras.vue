<template>
    <div v-on="busca()">
        <p>este es el componente Cuenta palabras
        </p>
    <button @click="busca()">presiona para contar</button>
    </div>
</template>

<script>
export default {
    name: 'CuentaPalabras',
    
}
</script>
