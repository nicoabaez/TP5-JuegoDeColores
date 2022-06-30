<template>

  <section class="src-componentes-header">
    <div id="header" :style="{'background': colorFondo()}">
      <h1>The Great <br><span id="colorDisplay">{{colorHijo}}</span><br>Guessing Game</h1>
    </div>
  </section>

</template>

<script lang="js">

  export default  {
    name: 'src-componentes-header',
    props: ['colorHijo', 'winner'],
    mounted () {

    },
    data () {
      return {
        
      }
    },
    methods: {
      colorFondo(){
        return this.winner == true ? this.colorHijo : 'steelblue';
      }
    },
    computed: {

    }
}


</script>

<style scoped lang="css">
h1 {
	font-weight: normal;
	line-height: 1.1;
	padding: 20px 0;

}
#header {
	transition: all 0.3s;
	text-transform: uppercase;
	text-align: center;
	margin: 0;
	color: white;
	
}
#colorDisplay {
	font-size: 200%;
}
</style>
