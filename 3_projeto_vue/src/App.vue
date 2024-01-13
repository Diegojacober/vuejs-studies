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
  <Watch/>
  <LifeCycle2/>
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
import Watch from './components/Watch.vue';
import LifeCycle2 from './components/LifeCycle2.vue';

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
    ComputedProperties,
    Watch,
    LifeCycle2
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