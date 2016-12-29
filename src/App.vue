<template>  
  <div id="app">
    <Cervejarias></Cervejarias>
    <!--<Lista></Lista>-->
    <!--<Botoes></Botoes>-->
    <!--<Formulario></Formulario>-->
  </div>
</template>

<script> 
import Cervejarias from './Cervejarias.vue'
  // import Lista from './Lista.vue'  
  // import Botoes from './Botoes.vue'
  // import Formulario from './Formulario.vue'
  export default {
    components: {
      Cervejarias
      // Lista
      // Botoes
      // Formulario
    }
  }
</script>  
<style>  
  body {
    margin-top: 50px
  }
</style>  