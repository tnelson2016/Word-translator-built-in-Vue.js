<template>
  <div id="app">
  <h1>Word Translator</h1>
  <h5>Powered by Vue.js</h5>
  <translateForm v-on:formSubmit="translateText"></translateForm>
</div>
</template>

<script>
import translateForm from './components/translateForm'

export default {
  name: 'App',
  components: {
    translateForm
  },
  methods: {
    translateText: function(text) {}
  }
}
</script>



<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
