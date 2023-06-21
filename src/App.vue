<template>
  <div id="app">
    <FormularioValidacion @formulario="handleFormulario"/>
    <hr/>
    <RenderElementos :datos="datosFormulario"/>
    <!-- <ModificadoresEntrada/>
    <hr/>
    <ModificadoresEventos/>
    <SelectDinamico :options=options 
    label="Select Dinamico" 
    id="dynamicSelect" 
    v-model="framework"/>
  v-model toma el valor desde adentro del selectDinamico, emitido por el inputHandler 
    <FormularioContacto />
    <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import FormularioContacto from './components/FormularioContacto.vue'
// import SelectDinamico from './components/SelectDinamico.vue'
// import ModificadoresEventos from './components/ModificadoresEventos.vue'
// import ModificadoresEntrada from './components/ModificadoresEntrada.vue'
import FormularioValidacion from './components/FormularioValidacion.vue'
import RenderElementos from './components/RenderElementos.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    // FormularioContacto,
   // SelectDinamico,
   // ModificadoresEventos,
   // ModificadoresEntrada,
    FormularioValidacion,
    RenderElementos


  },
  data() {
    return {
      datosFormulario:{},

      options:[
        {name: "Angular" , value: "angular"},
        {name: "Vue",value: "vue" },
        {name: "React",value: "react" },
        {name: "HTML",value: "html" }
      ],
      framework:""
    }
  },
  methods:{
    handleFormulario(model){
      this.datosFormulario=model;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
