<template>
  <div id="app">
  <h1>Word Translator</h1>
  <h5>Powered by Vue.js</h5>
  <translateForm v-on:formSubmit="translateText"></translateForm>
  <translateOutput v-text="translatedText"></translateOutput>
</div>
</template>

<script>
import translateForm from './components/translateForm'
import translateOutput from './components/translateOutput'

export default {
  name: 'App',
  components: {
    translateForm,
    translateOutput
  },
  data: function() {
    return {
      translatedText: ''
    }
  },
  methods: {
    translateText: function(text, language) {
      this.$http
        .get(
          'https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180422T204748Z.eb9b55d86498f560.cdc9e4f343a84245fed10909abba494e50524223&lang=' +
            language +
            '&text=' +
            text
        )

        .then(response => {
          this.translatedText = response.body.text[0]
        })
    }
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
