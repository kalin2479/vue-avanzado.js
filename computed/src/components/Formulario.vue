<template lang="pug">
  .boxPersonalInformation
    .boxData
      h2
        | Escriba su nombre completo:
      input(v-model="name")
      input(v-model="lastName")
      p
        | {{ fullName }}
    .boxBirthdate
      h2
        | Fecha de nacimiento (dd/mm/aaaa)
      input(v-model="birthdate")

      p
        | Mi edad es: {{ getAge }}

</template>

<script>
export default {
  // Este nombre debe coincidir con el nombre del componente que hemos definido
  // Las propiedades computadas, son propiedades que se calculan a partir de los valores de otras propiedades.
  // Esto quiere decir que podemos crear propiedades dinamicas que van hacer regeneradas cada vez que otras propiedades
  // cambien su valor.
  name: 'formulario',
  data () {
    return {
      name: '',
      lastName: '',
      birthdate: ''
    }
  },
  computed: {
    getAge: function () {
      let arr = this.birthdate.split('/')
      if (typeof arr[2] !== 'undefined') {
        let year = arr[2]
        if (year.length === 4) {
          let date = new Date()
          let yearNow = date.getFullYear()
          return yearNow - year
        }
      }
    },
    fullName () {
      // la funciones ha sido escrita en ES6
      // Utilizando los but tics `` es una manera optima de concatenar sin necesidad de utilizar
      // los espacios, esto  es gracias a template string EA6 o EA2015
      // Y se escribe las variables dentro de los simbolos pesos y las llaves
      return `${this.name} ${this.lastName}`
    }
  }
}
</script>
<!-- scoped lo que va hacer es poner ciertos id a los elementos o atributo de datos a los elementos
en cuestion y lo que va hacer en los estilos es aplicarlo a los estilos que tengan el data atribuit
de manera interna -->
<!-- Es una buena practica importar los archivos globales que vamos a utilzar -->
<style lang="sass" scoped>
  .boxPersonalInformation
    margin: 20px auto
    width: 400px
    border: 1px solid red
    text-align: center
    .boxData
      margin: 30px 0
</style>
