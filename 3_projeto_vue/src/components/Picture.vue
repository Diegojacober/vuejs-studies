<template>
    <img :src="avatar" :alt="descricao" height="120" width="120">
</template>
<script>
export default {
    name: 'Picture',
    data() {
        return {
            avatar: "https://avatars.githubusercontent.com/u/81656395?v=4",
            descricao: "Diego"
        }
    }
}
</script>