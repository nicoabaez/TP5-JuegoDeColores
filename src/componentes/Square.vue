<template>
<!-- En la implentación final tuve que usar los square como clase y no como componente, por eso está todo comentado -->
  <section class="src-componentes-square">
    <!-- <div
      class='square' 
      :style="{'background': miColor}" 
      @click="compararColores()" 
      
      /> -->
  </section>
</template>

<script lang="js">

  export default  {
    name: 'src-componentes-square',
    // props: ['colorRecibido','colorPrincipal','ganadorRecibido'],
    mounted () {
    },
    data () {
      return {  
        // miColor: this.colorRecibido,
      }
    },  
    methods: {
      // compararColores(){
      //   let mensaje;
      //   let colorMensaje;
      //   let mensajeReset;
      //   let win = false;
      //   if (this.colorRecibido === this.colorPrincipal) {
      //     win = true;
      //     mensaje = "You Picked Right!";
      //     colorMensaje = this.colorPrincipal;
      //     mensajeReset = "Play Again!";
      //   } else {
      //     win = false;
      //     this.miColor = this.establecerColorNeutro();
      //     mensaje = "Try Again!";
      //     colorMensaje = "#000000";
      //     mensajeReset = 'New Colors!';
      //   }
      //   this.isGanador = win;
      //   this.$emit('mensajeReset', mensajeReset);
      //   this.$emit('winner', win);
      //   this.$emit('mensaje', mensaje);
      //   this.$emit('colorMensaje', colorMensaje); 

      // },
      // establecerColorNeutro(){
      //   let colorRetorno = "#232323"
      //   if(this.ganadorRecibido){colorRetorno = this.colorPrincipal}
      //   console.log(colorRetorno)
      //   return colorRetorno;
      // } 
    },
    computed: {

    }
}


</script>

<style scoped>
  /* .square {
    width: 30%;
    padding-bottom: 30%;
    float: left;
    margin: 1.66%;
    border-radius: 10%;
    transition: background 0.8s;
    -webkit-transition: background 0.8s;
    -moz-transition: background 0.8s;
  } */

</style>
