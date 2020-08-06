<template>
  <div id="app">
    <ColorPicker :selectedColor="selectedColor" :pixels=pixels :color="color" />
    <Canvas :pixels=pixels :color="color" />
  </div>
</template>

<script>
import Canvas from './components/Canvas.vue';
import ColorPicker from './components/ColorPicker';

const defaultColor = 'white'

export default {
  name: 'App',
  components: {
    Canvas,
    ColorPicker
  },
  data: function() {
    return {
      color: defaultColor,
      isDrawing: false,
      selectedColor: defaultColor,
      pixels: {
        rows: 50,
        columns: 50
      }
    }
  },
  mounted() {
    this.$root.$on('updatecolor', color => {
      this.selectedColor = color;
      console.log(color)
    });
    this.$root.$on('drawPixel', (color, event) =>{
      if(this.isDrawing){
        console.log(event.target.classList);
        event.target.className = "pixel";
        event.target.classList.add(this.selectedColor);
      }
    });
    this.$root.$on('mouseDownOnPixel', () =>{
      this.isDrawing = true;
    });
    this.$root.$on('mouseUpOnPixel', () =>{
      this.isDrawing = false;
    });
    
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
    margin: 60px auto 20px auto;
    display: grid;
    width: 90%;
    grid-template-columns: 100px 1fr;
  }
  body {
    background-color: black;
  }
</style>
