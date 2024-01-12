<template lang="">
    <form @submit="enviarForm($event)">
        <InputeText/>
        <InputeText/>
        <input type="submit" value="Enviar">
    </form>
</template>

<script>
import InputeText from './form/InputText.vue'
export default {
    name: 'Form',
    components: {
        InputeText
    },
    methods: {
        enviarForm(e) {
            e.preventDefault();
            console.log('opa')
        }
    }
}
</script>