<template>
  <Header />
  <PrimeiroComponente />
  <LifeCycle />
  <Pessoa />
  <Form />
  <Reutilizacao/>
  <Reutilizacao/>
  <Reutilizacao/>
  <Reutilizacao/>

  <VModel/>
  <ComputedProperties/>
</template>

<script>
import PrimeiroComponente from './components/PrimeiroComponente.vue';
import LifeCycle from './components/LifeCycle.vue';
import Pessoa from './components/Pessoa.vue';
import Form from './components/Form.vue';
import Header from './components/Header.vue';
import Reutilizacao from './components/Reutilizacao.vue';
import VModel from './components/VModel.vue';
import ComputedProperties from './components/ComputedProperties.vue';

export default {
  name: 'App',
  components: {
    PrimeiroComponente,
    LifeCycle,
    Pessoa,
    Form,
    Header,
    Reutilizacao,
    VModel,
    ComputedProperties
}
}
</script>

<style>
body {
  background-color: #333;
  color: #fff;
}

a {
  color: #f00;
}
</style>