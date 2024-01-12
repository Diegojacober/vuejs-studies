<template>
    <div>
        <h2 @click="nomeAleatorio($event), printarNome(name, $event)">Esta é a descrição da pessoa: {{ name }}</h2>
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
        nomeAleatorio(e) {
            let nome = ['Diego', 'Pedro', 'João', 'Roberto'];
            this.name = nome[Math.floor(Math.random() * nome.length)]
        },
        printarNome(txt, e) {
            console.log(txt)
        }
    }
}
</script>