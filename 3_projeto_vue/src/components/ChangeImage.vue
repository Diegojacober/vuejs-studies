<template>
    <div>
        <button @click="$emit('changeImage')">Trocar imagem de perfil</button>
    </div>
</template>
<script>
export default {
    name: 'ChangeImage',
    emits: ['changeImage']
}
</script>
<style lang="">
    
</style>