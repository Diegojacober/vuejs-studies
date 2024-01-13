<template>
    <div>
        <input v-model="name" type="text">

        <br><br><br>
        <select v-model="pageCount">
            <option value="5">5</option>
            <option value="10">10</option>
            <option value="15">15</option>
            <option value="20">20</option>
        </select>

        {{ pageCount }}

        <br><br><br>

        <input type="text" v-model="user.first_name">
        <input type="text" v-model="user.last_name">
    </div>
</template>
<script>
import { handleError } from 'vue'

export default {
    name: 'Watch',
    data() {
        return {
            name: '',
            pageCount: 5,
            user: {
                first_name: '',
                last_name: '',
            }
        }
    },

    watch: {
        name(newValue, oldValue) {
            //quando acontecer algo em name, essa função vai ser executada
            // console.log(newValue, oldValue)
            this.saveUser()
        },
        pageCount(vl) {
            this.changePage()
        },
        // user() {
        //     console.log("User alterado")
        //     // so funciona se mudar o objeto inteiro
        // }
        user: {
            handler() {
                console.log("User alterado")
            },
            deep: true // qualquer coisa do objeto alterar, dispare
        }
    },
    methods: {
        saveUser() {
            console.log(this.name)
        },
        changePage(page) {
            console.log(this.pageCount)
        }
    }
}
</script>
<style lang="">
    
</style>