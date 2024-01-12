<template lang="">
    <form>
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
    }
}
</script>