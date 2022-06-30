<template lang="html">

  <section class="src-componentes-navigator">
    <div id="navigator">
      <button id="reset" @click="nuevoColor()">{{mensajeReset}}</button>
      <span id="message" :style="{'color': colorTexto()}"> {{mensaje}} </span>

      <button id="easy" @click="modoFacil()"   :class="{ selected: isFacil }" >easy</button>
      <button id="hard" @click="modoDificil()" :class="{ selected: !isFacil }">hard</button>
    </div>
  </section>

</template>

<script lang="js">

  export default  {
    name: 'src-componentes-navigator',
    props: ['mensaje','colorMensaje','mensajeReset'],
    mounted () {
    },
    data () {
      return {
		isFacil: null,
      }
    },
    methods: {
		modoFacil(){
			this.isFacil = true;
			this.nuevoColor();
		},
		modoDificil(){
			this.isFacil = false;
			this.nuevoColor();
		},
		nuevoColor(){
			// let nuevoColor = " (" + this.randomInt() + ", " + this.randomInt() + ", " + this.randomInt() + ")" ;
			// this.$emit('nuevoColor', nuevoColor);
			this.$emit('modo', this.isFacil);
			this.$emit('restart')
		},
		randomInt(){
			return Math.floor(Math.random() * 256);
		},
		colorTexto(){
			return this.colorMensaje || 'black'
		}
    },
    computed: {

    }
}


</script>

<style scoped lang="css">
button {
	border: none;
	background-color: white;
	font-family: "Montserrat", "Avenir";
	text-transform: uppercase;
	height: 100%;
	font-weight: 700;
	letter-spacing: 1px;
	color: steelblue;
	transition: all 0.3s;
	outline: none;
}
button:hover {
	color: white;
	background-color: steelblue;
}
.selected {
	background-color: steelblue;
	color: white;
}
#navigator {
	background: #ffffff;
	height: 30px;
	text-align: center;
	margin: 0;
	margin-top: -30px;

}
#message {
	color: #ffffff;
	display: inline-block;
	width: 20%;
}


</style>
