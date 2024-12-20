<template>
  <h2>{{ encabezado }}:{{ valor2 }}</h2>

  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputada }}</p>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputada }}</p>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputada }}</p>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputada }}</p>
  <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputada }}</p>

  <div>
    <button @:click="incrementar">+1</button>
    <button v-on:click="decrementar">-1</button>
  </div>

  <div v-if ="this.esVerdad">

    <h1>Feliz Navidad</h1>
  </div>

</template>
 
<script>
export default {
  data() {
    return {
      numero: this.valor,
      titulo: "Contador",
    };
  },
  methods: {
    calcularCuadrado() {
      console.log("Entro a calcular");
      return this.numero * this.numero;
    },

    incrementar() {
      this.numero++;
    },

    decrementar() {
      this.numero--;
    },
  },
  computed: {
    calcularCuadradoComputada() {
      console.log("Entro a calcular computada ");
      
      return this.numero * this.numero;
    },
  },
  //props:['encabezado','valor']
  props:{
    encabezado:{
      type:String,
      validator(encabezado){
        return !encabezado.includes('a')
      }
    },
    valor:Number,
    valor2:{
      type:Number,
      required:false,
      default:77,
      validator(value){
        //programo mi validacion bajo mi criterio
        //y retorno treu cuando es valido para mi 
        //retorno false cuando no es valido para mi 

        return value<=77
      }
    },
    esVerdad:{
      type:Boolean,
      required:true
    },
    arreglo:Array,
    fecha:Date,
    obejetoPersona:Object

  }
};
</script>
 
<style>
/* Add your styles here */

button {
  background: #64b687;
  border-radius: 10px;
  border: 1px solid white;
  color: white;
  cursor: pointer;
  margin: 0px 5px;
  padding: 5px 15px;
}
button:hover {
  background: #5aa67b;
}
</style>
 