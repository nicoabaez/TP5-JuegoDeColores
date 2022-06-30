<template>
  <!-- Este fue una manera fallida de hacerlo, pero que con algunos retoques quizás pueda llegar a funcionar -->
  <div class="jumbotron">
    <!-- 
      <Header 
        :winner="ganador" 
        :colorHijo="colorPrincipal"
      />
    <Navigator 
        :mensaje="mensaje"
        :colorMensaje="colorMensaje"
        :mensajeReset="mensajeReset"
        @restart="restart()"
        @modo="establecerModo($event)"
      />
    <div class="container">
      <p v-for="(square, index) in squares" :key="index">
        <Square 
          v-show="!ganador"
          :colorPrincipal="colorPrincipal"
          :colorRecibido="square.colorRecibido"
          :ganadorRecibido="ganador"
          @winner="verificarGanador($event)"   
          @mensaje="mensaje=$event"
          @colorMensaje="colorMensaje=$event"
          @mensajeReset="mensajeReset=$event"

        />
      </p>
      <p v-for="(square, index) in squares" :key="index-6" >
        <Square 
          v-show="ganador"
          :colorPrincipal="colorPrincipal"
          :colorRecibido="colorPrincipal"
          :ganadorRecibido="ganador"
          @winner="verificarGanador($event)"   
          @mensaje="mensaje=$event"
          @colorMensaje="colorMensaje=$event"
          @mensajeReset="mensajeReset=$event"
        />
      </p>
    </div> 
    <br>
    <hr>
    <button @click="blanquearColores()"> REVISAR </button> -->
  </div>
</template>

<script>
// import Header from "./componentes/Header"
// import Navigator from "./componentes/Navigator"
// import Square from "./componentes/Square"

export default {
  name: 'App',
  components: {
    // Header,
    // Navigator,
    // Square
  },
  mounted () {
    // this.iniciarJuego()
  },
  data () {
    return{ 
    //   esFacil: false,
    //   colors: [],
    //   squares: [],
    //   square:{
    //     colorRecibido: 'white',
    //   },
    //   colorPrincipal: null,
    //   colorCount: 0, 
    //   ganador: false,
    //   mensaje: null,
    //   colorMensaje: null,
    //   mensajeReset: 'New Colors!',
    }
  },
  methods:{
    // iniciarJuego(){
    //   this.restart();
    // },
    // restart(){
    //   this.colors  = [];
    //   this.squares = [];
    //   this.ganador = false;
    //   this.colorCount = 0;
    //   this.esFacil = false
    //   this.square.colorRecibido = 'white'
    //   this.colorPrincipal = null

    //   this.establecerModo(this.esFacil);
    //   this.crearColores()
    //   this.obtenerCuadrados();
    //   this.establecerColorPrincipal()


    // },
    // obtenerCuadrados(){
    //   for (var i = 0; i < this.getColorCount(); i++){
    //     let newSquare = {}
    //     this.squares.push(newSquare)
    //     this.squares[i].colorRecibido = this.colors[i];
    //   }
    // },
    // crearColores(){
    //   this.colors = this.createNewColors(this.getColorCount());
    // },
    // establecerColorPrincipal(){
    //   this.colorPrincipal = this.colors[this.seleccionarColor()];
    // },
    // seleccionarColor(){
    //   return Math.floor(Math.random() * this.getColorCount() );
    // },
    // establecerModo(modo){
    //   this.esFacil = modo;
    //   let resultado
    //   if(modo){
    //     resultado = 3
    //   } else {
    //     resultado = 6
    //   }
    //   this.colorCount = resultado;
    // },
    // verificarGanador(ganador){
    //   if(ganador){
    //     this.ganador = true;
    //     this.setAllColorsTo(this.colorPrincipal)
    //   }
    // },
    // setAllColorsTo(color){
    //   for(var i = 0; i < 6; i++){
    //     this.squares[i].colorRecibido = color;
    //   }
    // },
    // createNewColors(numbers){
    //   var arr = [];
    //   for (var i = 0; i < numbers; i++) {
    //     arr.push(this.createRandomStringColor());
    //   }
    //     return arr;
    // },
    // createRandomStringColor(){
    //   var newColor = "rgb(" + this.randomInt() + ", " + this.randomInt() + ", " + this.randomInt() + ")" ;
    //   return newColor;
    // },
    // randomInt(){
    //   return Math.floor(Math.random() * 256);
    // },
    // getColorCount(){
    //   return this.colorCount;
    // },
  }
}
</script>

<style scoped lang="css">
  /* .container {
    margin: 20px auto;
    max-width: 600px;
  } */
</style>