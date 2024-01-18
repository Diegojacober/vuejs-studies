<template>
    <Message :msg="msg" v-show="msg" />
    <div id="burguer-table">
        <div>
            <div id="burguer-table-heading">
                <div class="order-id">#: </div>
                <div>Cliente:</div>
                <div>Pão:</div>
                <div>Carne:</div>
                <div>Opcionais:</div>
                <div>Ações:</div>
            </div>
        </div>
        <div id="burguer-table-rows">
            <div class="burguer-table-row" v-for="burguer in burgers" :key="burguer.id">
                <div class="order-number">{{ burguer.id }}</div>
                <div>{{ burguer.nome }}</div>
                <div>{{ burguer.pao }}</div>
                <div>{{ burguer.carne }}</div>
                <div>
                    <ul>
                        <li v-for="(opcional, index) in burguer.opcionais">{{ opcional }}</li>
                        <li>Tomate</li>
                    </ul>
                </div>

                <div>
                    <select name="status" class="status" @change="updateBurguerStatus($event, burguer.id)">
                        <option value="">Selecione</option>
                        <option v-for="s in status" :key="s.id" :value="s.tipo" :selected="burguer.status == s.tipo">{{
                            s.tipo }}</option>
                    </select>
                    <button class="btn-delete" @click="deleteBurguer(burguer.id)">Cancelar</button>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import Message from './Message.vue';

export default {
    name: "Dashboard",
    data() {
        return {
            burgers: null,
            burger_id: null,
            status: [],
            msg: ""
        };
    },
    methods: {
        async getStatus() {
            const req = await fetch("http://localhost:3000/status");
            const data = await req.json();
            this.status = data;
        },
        async getPedidos() {
            const req = await fetch("http://localhost:3000/burgers");
            const data = await req.json();
            this.burgers = data;
            this.getStatus();
        },
        async deleteBurguer(id) {
            const req = await fetch(`http://localhost:3000/burgers/${id}`, {
                method: "DELETE"
            });
            const res = await req.json();
            this.burgers = this.burgers.filter(burguer => burguer.id !== id);

            this.msg = `Pedido Nº ${res.id} deletado com sucesso!`

            setTimeout(() => this.msg = "", 3000)
        },
        async updateBurguerStatus(event, id) {
            const option = event.target.value;
            const dataJson = JSON.stringify({ status: option });
            const req = await fetch(`http://localhost:3000/burgers/${id}`, {
                method: "PATCH",
                headers: { "Content-Type": "application/json" },
                body: dataJson
            });
            const res = await req.json();

            this.msg = `Pedido Nº ${res.id} atualizado com sucesso!`

            setTimeout(() => this.msg = "", 3000)
        }
    },
    mounted() {
        this.getPedidos();
    },
    components: { Message }
}
</script>
<style scoped>
#burguer-table {
    max-width: 1200px;
    margin: 0 auto;
}

#burguer-table-heading,
#burguer-table-rows,
.burguer-table-row {
    display: flex;
    flex-wrap: wrap;
}

#burguer-table-heading {
    font-weight: bold;
    padding: 12px;
    border-bottom: 3px solid #333;
}

.burguer-table-row {
    width: 100%;
    padding: 12px;
    border-bottom: 1px solid #CCC;
}

#burguer-table-heading div,
.burguer-table-row div {
    width: 19%;
}

#burguer-table-heading .order-id,
.burguer-table-row .order-number {
    width: 5%;
}

select {
    padding: 12px 6px;
    margin-right: 12px;
}

.btn-delete {
    background-color: #222;
    color: #fcba03;
    font-weight: bold;
    border: 2px solid #222;
    padding: 10px;
    font-size: 16px;
    margin: 0 auto;
    cursor: pointer;
    transition: .5s;
}

.btn-delete:hover {
    background-color: transparent;
    color: #222;
}
</style>