<template>
    <div>
        <h2 @click="nomeAleatorio">Esta é a descrição da pessoa: {{ name }}</h2>
        <Info/>
    </div>
</template>

<script>
import Info from './Info.vue';

    export default {
    name: 'LifyCycle',
    data() {
        return {
            name: 'Diego'
        };
    },
    components: { Info },
    methods: {
        nomeAleatorio() {
            let nome = ['Diego', 'Pedro', 'João', 'Roberto'];
            this.name = nome[Math.floor(Math.random() * nome.length)]
        }
    }
}
</script>