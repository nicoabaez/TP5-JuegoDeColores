<template>
  <div class="jumbotron">
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
        <div class="square" 
          v-for="(square, index) in squares" :key="index"
          :style="{'background-color': square.colorRecibido}"
          @click="compararColores(squares[index])"
        />
    </div> 
  </div>
</template>

<script>
import Header from "./componentes/Header"
import Navigator from "./componentes/Navigator"

export default {
  name: 'App',
  components: {
    Header,
    Navigator,
  },
  mounted () {
    this.iniciarJuego()
  },
  data () {
    return{ 
      esFacil: false,
      colors: [],
      squares: [],
      square:{
        colorRecibido: 'white',
      },
      colorPrincipal: null,
      colorCount: 0, 
      ganador: false,
      mensaje: null,
      colorMensaje: null,
      mensajeReset: 'New Colors!',
    }
  },
  methods:{
    ver(){
      console.log(this.squares)
      console.log(this.colors)
    },
    setColorRecibido(i,color){
      this.squares[i].colorRecibido = color
    },
    iniciarJuego(){
      this.restart();
    },
    restart(){
      this.colors  = [];
      this.squares = [];
      this.ganador = false;
      this.colorCount = 0;
      this.colorPrincipal = null

      this.establecerModo(this.esFacil);      
      this.crearColores()
      this.obtenerCuadrados();
      this.establecerColorPrincipal()
    },
    crearColores(){
      this.colors = this.createNewColors(this.getColorCount());
    },
    obtenerCuadrados(){
      for (var i = 0; i < this.getColorCount(); i++){
        let newSquare = {}
        this.squares.push(newSquare)
        this.setColorRecibido(i, this.colors[i])
      }
    },
    establecerColorPrincipal(){
      this.colorPrincipal = this.colors[this.seleccionarColor()];
    },
    seleccionarColor(){
      return Math.floor(Math.random() * this.getColorCount() );
    },
    establecerModo(modo){
      this.esFacil = modo;
      let resultado
      if(modo){
        resultado = 3
      } else {
        resultado = 6
      }
      this.colorCount = resultado;
    },
    verificarGanador(ganador){
      if(ganador){
        this.ganador = true;
        this.setAllColorsTo(this.colorPrincipal)
      }
    },
    setAllColorsTo(color){
      for(var i = 0; i < 6; i++){
       this.setColorRecibido(i, color);
      }
    },
    createNewColors(numbers){
      var arr = [];
      for (var i = 0; i < numbers; i++) {
        arr.push(this.createRandomStringColor());
      }
        return arr;
    },
    createRandomStringColor(){
      var newColor = "rgb(" + this.randomInt() + ", " + this.randomInt() + ", " + this.randomInt() + ")" ;
      return newColor;
    },
    randomInt(){
      return Math.floor(Math.random() * 256);
    },
    getColorCount(){
      return this.colorCount;
    },
    compararColores(cuadrado){
      if (cuadrado.colorRecibido === this.colorPrincipal) {
        this.ganador = true;
        this.mensaje = "You Picked Right!";
        this.colorMensaje = this.colorPrincipal;
        this.mensajeReset = "Play Again!";
        this.setAllColorsTo(this.colorPrincipal)
      } else {
        this.ganador = false;
        this.noCoincide(cuadrado)
        this.mensaje = "Try Again!";
        this.colorMensaje = "#000000";
        this.mensajeReset = 'New Colors!';
      }
    },
    noCoincide(square){
      square.colorRecibido = '#232323'
      console.log('NO COINCIDE')
    }
  }
}
</script>

<style scoped lang="css">
  .container {
    margin: 20px auto;
    max-width: 600px;
  }
  .square {
    width: 30%;
    padding-bottom: 30%;
    float: left;
    margin: 1.66%;
    border-radius: 10%;
    transition: background 0.8s;
    -webkit-transition: background 0.8s;
    -moz-transition: background 0.8s;
  }

</style>