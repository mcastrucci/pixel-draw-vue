<template>
  <div class="colorpicker">
    <Pixel isInColorPicker color="white" :current="selectedColor == 'white' ? true : false"/>
    <Pixel isInColorPicker color="lightblue" :current="selectedColor == 'lightblue' ? true : false"/>
    <Pixel isInColorPicker color="blue" :current="selectedColor == 'blue' ? true : false"/>
    <Pixel isInColorPicker color="darkblue" :current="selectedColor == 'darkblue' ? true : false"/>

    <Pixel isInColorPicker color="lavender-rose" :current="selectedColor == 'lavender-rose' ? true : false"/>
    <Pixel isInColorPicker color="holy-hock" :current="selectedColor == 'holy-hock' ? true : false"/>
    <Pixel isInColorPicker color="leagues" :current="selectedColor == 'leagues' ? true : false"/>
    <Pixel isInColorPicker color="pixelated-grass" :current="selectedColor == 'pixelated-grass' ? true : false"/>

    <Pixel isInColorPicker color="red-pigment" :current="selectedColor == 'red-pigment' ? true : false"/>
    <Pixel isInColorPicker color="puffin-bills" :current="selectedColor == 'puffin-bills' ? true : false"/>
    <Pixel isInColorPicker color="radiant-yellow" :current="selectedColor == 'radiant-yellow' ? true : false"/>
    <Pixel isInColorPicker color="forgotten-purple" :current="selectedColor == 'forgotten-purple' ? true : false"/>
  </div>
</template>

<script>
import Pixel from './Pixel'

export default {
  name: 'ColorPicker',
  components: {
    Pixel
  },
  props: {
      color: String,
      selectedColor: String
  }
}
</script>

<style scoped>
    .colorpicker{
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    .pixel {
        width: 100px;
        height: 100%;
        cursor: pointer;
    }
</style>