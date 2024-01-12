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
    </div>
</template>

<script>
export default {
    name: 'Info',
    data() {
        return {
            is_working: true,
            show_email: true
        }
    }
}
</script>