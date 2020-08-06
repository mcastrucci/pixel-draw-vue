<template>
    <div class="canvas">
        <Pixel isInCanvas v-for="n in (pixels.rows * pixels.columns)" :key="n" :color="color" />
    </div>
</template>

<script>
    import Pixel from './Pixel'

    export default {
        name: 'Canvas',
        components: {
            Pixel
        },
        props: {
            color: String,
            isDrawing: Boolean,
            pixels: {
                type: Object,
                default: ()=> {
                    return ({
                        columns: 2,
                        rows: 2
                    });
                }
            }
        }
    }
</script>

<style>
    .canvas {
        display: grid;
        grid-template-columns: repeat(50, 1fr);
        grid-template-rows: repeat(50, 1fr);
        justify-content: stretch;
        height: 80vh;
    }
</style>