<template>
    <div>
        <h1>Olá vue!</h1>
        <p>Meu nome é {{ name }}</p>
    </div>
</template>

<script>
export default {
    name: 'Primeiro componente',
    data() {
        return {
            // so podem ser usados nesse componente
            name: "Diego"
        }
    }
}
</script>