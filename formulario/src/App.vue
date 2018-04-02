<template lang="pug">
  #app
    formulario
</template>

<script>
import Formulario from './components/Formulario.vue'
export default{
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    Formulario: Formulario
  }
}
</script>
<!-- scoped lo que va hacer es poner ciertos id a los elementos o atributo de datos a los elementos
en cuestion y lo que va hacer en los estilos es aplicarlo a los estilos que tengan el data atribuit
de manera interna -->
<!-- Es una buena practica importar los archivos globales que vamos a utilzar -->
<style lang="sass">
  @import './sass/main.sass'
</style>
