<template>
    <div>
       <h2> Propriedades que dependem de outras para serem computadas</h2>
       <button @click="click">Click</button>
       <p>{{ fullName }}</p>
    </div>
</template>
<script>
export default {
    name: 'ComputedProperties',
    data() {
        return {
            first_name: 'Diego',
            last_name: 'Jacober'
        }
    },
    computed: {
        fullName() {
            // fica em cache e é recomputado quando modificar um valor
            return `${this.first_name} ${this.last_name}`;
        }
    },
    methods: {
        click() {
            console.log(this)
        }
    }
}
</script>
<style scoped>
    div {
        margin-top: 50px;
    }
</style>