<template lang="pug">
.boxForm
  form(class="box", @submit.prevent="submit", action="", method="post")
    .boxRow
      img(src="../assets/logo.jpg")
    .boxRow
      h2
        | {{ titulo }}
    .boxRow
      label Nombre
      input(type="text" v-model="arrdatos.nombre" placeholder="Ingresa tu nombre")
    .boxRow
      label Apellido
      input(type="text" v-model="arrdatos.apellido" placeholder="Ingresa tu apellido")
    .boxRow
      label Cargo
      input(type="text" v-model="arrdatos.cargo" placeholder="Ingresa tu cargo")
    .boxRow.boxBottom(v-show="!loading")
      button(type="submit") Enviar
    .boxRow.boxMsje(v-show="loading")
      p
        | Procesando su información
</template>

<script>
export default {
  // Este nombre debe coincidir con el nombre del componente que hemos definido
  name: 'formulario',
  data () {
    return {
      titulo: 'Registro estación Platzi',
      arrdatos: {
        nombre: '',
        apellido: '',
        cargo: ''
      },
      loading: false
    }
  },
  methods: {
    submit: function () {
      const self = this
      this.loading = true
      setTimeout(function () {
        console.log('hola')
        console.log(self.arrdatos)
        self.arrdatos = []
        self.loading = false
      }, 3000)
    }
  }
}
</script>
<!-- scoped lo que va hacer es poner ciertos id a los elementos o atributo de datos a los elementos
en cuestion y lo que va hacer en los estilos es aplicarlo a los estilos que tengan el data atribuit
de manera interna -->
<!-- Es una buena practica importar los archivos globales que vamos a utilzar -->
<style lang="sass" scoped>
  .boxForm
    display: grid
    grid-template-columns: 320px
    justify-content: center
    align-content: center
    height: 100vh
    form
      display: grid
      justify-content: center
      align-content: center
      .boxRow
        margin-bottom: 18px
        &:first-child
          text-align: center
          margin-bottom: 10px
          img
            margin: auto
        &:nth-of-type(2)
          margin-bottom: 10px
        &.boxMsje
          p
            font-size: 12px
            font-family: "Roboto"
            font-weight: 400
            color: rgb(252, 61, 56)
            text-align: right
        &.boxBottom
          display: flex
          justify-content: flex-end
          padding-top: 18px
          button
            cursor: pointer
            width: 150px
            border: 0
            font-size: 18px
            font-family: "Roboto"
            font-weight: 700
            color: #fff
            text-align: center
            line-height: 2.2em
            background: #00bfd6
        h2
          font-size: 24px
          font-family: "Roboto"
          font-weight: 900
          color: #00bfd6
          text-align: left
        label
          display: block
          font-size: 12px
          font-family: "Roboto"
          font-weight: 700
          color: #ff9300
        input[type="text"]
          display: block
          border: 0
          border-bottom: 1px solid #ff9300
          width: 100%
          height: 30px
          font-size: 16px
          font-family: "Roboto"
          font-weight: 400
</style>
