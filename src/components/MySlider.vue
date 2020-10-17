<template>
    <div class="slider">
        <button class="slider__btn--prev" :disabled="start" @click="changeSlide(-1)">P</button>

        <div class="slides">
         
            <img :src="getImgUrl(images[currentIndex].url)" /> 

        </div>

        <button class="slider__btn--next" :disabled="end" @click="changeSlide(1)">N</button>
    </div>
</template>

<script>
export default {
    name: 'my-slider',
    props: {
        images: Array
    },
    data() {
        return {
            
            timer: null,
            currentIndex: 0
        }
    },
    mounted: 
        function() {
            window.setInterval(() => {
            this.next();
            }, 5000);
    },
    methods: {

        getImgUrl(im) {
            return require('../assets/photo' + im);
        },
    
        changeSlide(dir) {

            let index = this.currentIndex + dir;

            let slide = this.images[index];

            if(slide !== undefined) {
                this.currentIndex = index;
            }
        },

        next() {
            this.currentIndex +=1;
            if(this.currentIndex === this.images.length) {
                this.currentIndex = 0;
            }
        }
    },
    computed: {
         start() {
            return this.currentIndex === 0;
        },

        end() {
            return this.currentIndex === this.images.length -1;
        }
    }    
}
</script>