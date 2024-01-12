<template>
    <div>
        <p v-if="is_working">Estou trabalhando no momento.</p>
        <p v-else>Não estou trabalhando no momento.</p>
        <p v-show="show_email">diegoalencar.jacober@gmail.com</p>
        <p>Utilizo as seguintes tecnologias:</p>
        <ul>
            <li>javascript</li>
            <li>php</li>
            <li>python</li>
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
            link: "https://github.com/diegojacober"
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