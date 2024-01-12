<template>
    <img :src="avatar" :alt="descricao" height="120" width="120">
    <ChangeImage @change-image="trocarImagem"/>
</template>
<script>
import ChangeImage from './ChangeImage.vue';

export default {
    name: 'Picture',
    data() {
        return {
            avatar: "https://avatars.githubusercontent.com/u/81656395?v=4",
            descricao: "Diego"
        };
    },
    components: { ChangeImage },
    methods: {
        trocarImagem() {
            this.avatar = this.avatar = "https://avatars.githubusercontent.com/u/156379818?v=4"
        }
    }
}
</script>