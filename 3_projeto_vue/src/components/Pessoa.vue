<template>
    <div>
        <h2 @click="nomeAleatorio($event), printarNome(name, $event)">Esta é a descrição da pessoa: {{ name }}</h2>
        <Info :email="email" :is_working="true"/>
    </div>
</template>

<script>
import Info from './Info.vue';

    export default {
    name: 'LifyCycle',
    data() {
        return {
            name: 'Diego',
            email: "diegoalencarj04@gmail.com"
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