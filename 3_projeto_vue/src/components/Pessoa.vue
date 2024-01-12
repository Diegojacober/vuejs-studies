<template>
    <div>
        <h2>Esta é a descrição da pessoa: {{ name }}</h2>
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
    components: { Info }
}
</script>