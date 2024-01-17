<template>
    <p>Burguer form component</p>
    <div>
        <form id="burguer-form">
            <div class="input-container">
                <label for="name">Nome do cliente:</label>
                <input type="text" id="name" name="name" v-model="name" placeholder="Digite seu nome">
            </div>
            <div class="input-container">
                <label for="bread">Escolha o pão:</label>
                <select name="bread" id="bread" v-model="bread">
                    <option value="">Selecione seu pão</option>
                    <option v-for="selectedBread in breads" :key="selectedBread.id" :value="selectedBread.tipo">
                        {{ selectedBread.tipo }}
                    </option>
                </select>
            </div>
            <div class="input-container">
                <label for="carne">Escolha a carne do seu Burguer:</label>
                <select name="carne" id="carne" v-model="meat">
                    <option value="">Selecione sua carne</option>
                    <option v-for="selectedMeat in breads" :key="selectedMeat.id" :value="selectedMeat.tipo">
                        {{ selectedMeat.tipo }}
                    </option>
                </select>
            </div>
            <div id="optionals-container" class="input-container">
                <label for="optionals" id="optionals-label">Selecione os opcionais:</label>
                <div class="checkbox-container" v-for="selectedOptional in optionalsData" :key="selectedOptional.id">
                    <input type="checkbox" name="optionals" v-model="optionals" :value="selectedOptional.tipo">
                    <span>{{ selectedOptional.tipo }}</span>
                </div>
            </div>
            <div class="input-container">
                <input type="submit" class="submit-btn" value="Criar meu Burguer!">
            </div>
        </form>
    </div>
</template>
<script>
export default {
    name: "BurguerForm",
    data() {
        return {
            breads: null,
            meats: null,
            optionalsData: null,
            name: null,
            bread: null,
            meat: null,
            optionals: [],
            status: "Solicitado",
            msg: null
        }
    },
    methods: {
        async getRecipes() {
            const req = await fetch("http://localhost:3000/ingredientes");
            const data = await req.json();

            this.breads = data.paes;
            this.meats = data.carnes;
            this.optionalsData = data.opcionais;
        }
    },
    mounted() {
        this.getRecipes();
    }
}
</script>
<style scoped>
#burguer-form {
    max-width: 400px;
    margin: 0 auto;
}

.input-container {
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
}

label {
    font-weight: bold;
    margin-bottom: 15px;
    color: #222;
    padding: 5px 10px;
    border-left: 4px solid #fcba03;
}

input,
select {
    padding: 5px 10px;
    width: 300px;
}

#optionals-container {
    flex-direction: row;
    flex-wrap: wrap;
}

#optionals-label {
    width: 100%;
}

.checkbox-container {
    display: flex;
    align-items: flex-start;
    width: 50%;
    margin-bottom: 20px;
}

.checkbox-container span,
.checkbox-container input {
    width: auto;
}

.checkbox-container span {
    margin-left: 6px;
    font-weight: bold;
}

.submit-btn {
    background: #222;
    color: #fcba03;
    font-weight: bold;
    border: 2px solid #222;
    padding: 10px;
    font-size: 16px;
    margin: 0 auto;
    cursor: pointer;
    transition: all ease-in .5s;
}

.submit-btn:hover {
    background: transparent;
    color: #222;
}
</style>