<template>
   <ul>
    <li><a href="@">Imagens</a></li>
    <li><a href="#">Home</a></li>
    <li><a href="@">Contato</a></li>
   </ul>
</template>
<script>
export default {
    name: 'Header'
}
</script>
<style scoped>
    ul {
        list-style: none;
        display: flex;
        background-color: #9999;
    }

    li{
        margin-right: 10px;
    }

    li a {
        color: rgb(87, 47, 122);
    }
</style>