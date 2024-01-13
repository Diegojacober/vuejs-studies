<template>
    <div>
       <div>
        Two-way data binding
        v-model -> formulários
       </div>
       <!-- one way data binding -->
       <!-- <p :class="var"> opa</p>  -->

       <label>Nome</label>
       <input v-model="name" type="text">
       {{ name }}

       <div>
        <label>Sports</label>
        <select v-model="sports">
            <option value="">Escolha</option>
            <option value="futebol">Futebol</option>
            <option value="basquete">Basquete</option>
            <option value="vvolei">Volei</option>
            <option value="volei">Volei</option>
        </select>
       </div>
    </div>
</template>
<script>
export default {
    name: 'VModel',
    data() {
        return {
            var: 'red',
            name: 'Diego',
            sports: ""
        }
    }
}
</script>
<style scoped>
    .red {
        color: #f00;
        border: 1px solid red;
        padding: 5px;
    }
</style>