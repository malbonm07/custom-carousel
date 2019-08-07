<template>
    <div class="carousel" style="position: relative; overflow: hidden;" width="100%">
        <slot></slot>
        <button class="carousel__nav carousel__next" @click.prevent="next">next</button>
        <button class="carousel__nav carousel__prev" @click.prevent="prev">prev</button>
    </div>
</template>

<script>
export default {
    data: () => {
        return {
            index: 0,
            slides: [],
            direction: ''
        }
    },
    methods: {
        next() {
            this.direction = 'Right'
            this.index++
        },
        prev() {
            this.direction = 'Left'
            this.index--
        }
    },
    watch: {
        index() {
            if(this.index >= this.slides.length) {
                this.index = 0
            }
            if(this.index < 0) {
                this.index = this.slides.length - 1
            }
        }
    },
    mounted() {
        this.slides = this.$children
        this.slides.forEach((slide, i) => {
            slide.index = i
        })
    }
}
</script>

<style lang="scss">
.carousel {
    background: red;
    .carousel__next {
        position: absolute;
        right: 0;
        bottom: 50%;
    }
    .carousel__prev {
        position: absolute;
        left: 0;
        bottom: 50%;
    }
}
</style>
