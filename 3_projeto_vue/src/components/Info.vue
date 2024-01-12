<template>
    <div>
        <p v-if="is_working">Estou trabalhando no momento.</p>
        <p v-else>Não estou trabalhando no momento.</p>
        <p v-show="show_email">diegoalencar.jacober@gmail.com</p>
        <p>Utilizo as seguintes tecnologias:</p>
        <ul v-for="tec, i in tecnologies" v-bind:key="i">
            <li >{{ tec }}</li>
        </ul>
        <ul v-for="front in front_end" :key="front.id">
            <li >{{ front.name }}</li>
        </ul>
        <div>
            <button @click="showEmail"> {{ show_email ? 'Ocultar e-mail' : 'Mostrar e-mail' }}</button>
        </div>
        <p>Para acessar o portfolio acesse <a v-bind:href="link">aqui</a></p>
        <Picture/>
    </div>
</template>

<script>
import Picture from './Picture.vue';

export default {
    name: 'Info',
    data() {
        return {
            is_working: true,
            show_email: false,
            link: "https://github.com/diegojacober",
            tecnologies: [
                "JavaScript",
                "PHP",
                "Python"
            ],
            front_end: [
                {id: 1, name: 'CSS'},
                {id: 2, name: 'VUE'},
                {id: 3, name: 'HTML'},
            ]
        };
    },
    components: { Picture },
    methods: {
        showEmail() {
            this.show_email = !this.show_email
        }
    }
}
</script>