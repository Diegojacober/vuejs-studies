<template>
    <div>
        <header v-if="showHeader">
            <p>Header aqui</p>
        </header>
        <h1>Hello world</h1>
        {{ name }}

        <button @click="showHeader = !showHeader">
            Ativar e desativar header
        </button>
    </div>
</template>
<script>
export default {
    name: 'LifeCycle2',
    data() {
        return {
            name: 'Diego',
            showHeader: true,
        }
    },
    // Criação
        // Preparar o componente
        // Ajax, inicializar algumas variáveis
        // Não tem acesso ao template (DOM)
    // Montagem
        // Inicializar um lib externa
        // Precisa de acesso ao template (DOM)
        // Tem acesso ao template (DOM)
    // Atualização
        // Debug
        // Update
    // Desmontagem
        // Remover tudo que for necessário (lib->destroy)
        // Liberar memória

    //HOOKS
    beforeCreate() {
        console.log('beforeCreate')
        console.log(this.name)
        console.log('DOM:', this.$el)

    },
    created() {
        console.log('created')
        console.log(this.name)
        console.log('DOM:', this.$el)
    },
    beforeMount() {
        console.log('beforeMount')
        console.log(this.name)
        console.log('DOM:', this.$el)

    },
    mounted() {
        console.log('mounted')
        console.log(this.name)
        console.log('DOM:', this.$el)
        window.addEventListener('resize', this.resize)
    },
    beforeUnmount() {
        console.log('beforeUnmount')
        console.log(this.name)
        console.log('DOM:', this.$el)
        window.removeEventListener('resize', this.resize)
    },
    unmounted() {
        console.log('unmounted')
        console.log(this.name)
        console.log('DOM:', this.$el)

    },
    methods: {
        resize($evt) {
            console.log($evt)
        }
    }
}
</script>
<style lang="">
    
</style>