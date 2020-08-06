<template>
  <div 
    @mouseup="handleMouseUp(color)" 
    @mousedown="handleMouseDown(color, $event)" 
    @mouseover="handleMouseOver(color, $event)"
    :class="['pixel', color, current ? 'current' : '']">
  </div>
</template>

<script>
  export default {
      name: 'Pixel',
      props: {
        color: String,
        current: Boolean,
        isInColorPicker: Boolean,
        isInCanvas: Boolean,
      },
      methods: {
        handleMouseDown: function (color, event) {
          if (this.isInCanvas) {
                  this.$root.$emit('mouseDownOnPixel');
          }
          if (this.isInCanvas) {
            this.$root.$emit('drawPixel', color, event);
          }
        },
        handleMouseUp: function (color) {
          if (this.isInColorPicker) {
            this.$root.$emit('updatecolor', color)
          }
          if (this.isInCanvas) {
              this.$root.$emit('mouseUpOnPixel');
          }
        },
        handleMouseOver: function (color, event) {
          if (this.isInCanvas) {
            this.$root.$emit('drawPixel', color, event);
          }
        }   
      }
  }
</script>
<style scoped>
.pixel {
  box-sizing: border-box;
  cursor: crosshair;
}

.white {
  background-color: white;
}
.lightblue {
  background-color: rgb(0, 188, 212);
}
.blue {
  background-color: rgb(3, 169, 244);
}
.darkblue {
  background-color: rgb(33, 150, 243);
}
.pixel.current {
  border: 3px green solid;
}

.lavender-rose{
  background-color: #FDA7DF;
}
.holy-hock{
  background-color: #833471;
}
.leagues{
  background-color: #1B1464;
}
.pixelated-grass{
  background-color: #009432;
}
.red-pigment{
  background-color: #EA2027;
}
.puffin-bills{
  background-color: #EE5A24;
}
.radiant-yellow{
  background-color: #F79F1F;
}
.forgotten-purple{
  background-color: #9980FA;
}

</style>