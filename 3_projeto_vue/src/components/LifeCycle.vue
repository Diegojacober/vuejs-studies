<template>
    <div>
        <h4>Meu nome é {{ name }}</h4>
    </div>
</template>

<script>
    export default {
        name: 'LifyCycle',
        data() {
            return {
                name: 'n sei'
            }
        },
        created() {
            setTimeout(() => {
                this.name = "Diego"
            }, 1000)
            
        },
        mounted() {
            setTimeout(() => {
                this.name = "Pedro"
            }, 2000)
        }
    }
</script>