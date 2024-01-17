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
                    <option value="integral">integral</option>
                </select>
            </div>
            <div class="input-container">
                <label for="carne">Escolha a carne do seu Burguer:</label>
                <select name="carne" id="carne" v-model="meat">
                    <option value="">Selecione sua carne</option>
                    <option value="maminha">maminha</option>
                </select>
            </div>
            <div id="optionals-container" class="input-container">
                <label for="optionals" id="optionals-label">Selecione os opcionais:</label>
                <div class="checkbox-container">
                    <input type="checkbox" name="optionals" v-model="optionals" value="Salame">
                    <span>Salame</span>
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
    name: "BurguerForm"
}
</script>
<style scoped>
    #burguer-form{
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

    input, select {
        padding: 5px 10px;
        width: 300px;
    }

    #optionals-container {
        flex-direction: row;
        flex-wrap: wrap;
    }

    #optionals-label{
        width: 100%;
    }

    .checkbox-container {
        display: flex;
        align-items: flex-start;
        width: 50%;
        margin-bottom: 20px;
    }

    .checkbox-container span, .checkbox-container input {
        width: auto;
    }

    .checkbox-container span {
        margin-left: 6px;
        font-weight: bold;
    }

    .submit-btn{
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