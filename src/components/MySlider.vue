<template>
    <div class="slider">
            <div class="slide">
                <button class="slide__btn slide__btn--prev" :disabled="start" @click="changeSlide(-1)">&lt;</button>
                
                    <img class="slide__img" :src="getImgUrl(images[currentIndex].url)" />
               
                <button class="slide__btn slide__btn--next" :disabled="end" @click="changeSlide(1)">&gt;</button>
            </div>
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

<style lang="scss" scoped>

@import "../styles/variables.scss";
@import "../styles/mixins.scss";

.slider {
    max-width: 100%;
}

.slide {
    position: relative;
    z-index: 2;

    &__btn {
        position: absolute;
        height: 4rem;
        width: 2rem;
        opacity: .5;
        z-index: 1000;
        border: none;
        font-weight: bold;
        font-size: 1.2rem;
        color: $background-top;
        outline: none;
        cursor: pointer;

        &:hover {
            opacity: 1;
        }
    }

    &__btn--prev {
        top: 45%;
        left: 0;
    }

     &__btn--next {
        top: 45%;
        right: 0;
    }

    &__img {
        max-width: 100%;
    }
}


@media all and (max-width: 480px) {
    .slide__btn {
        display: none;
    }
}

</style>