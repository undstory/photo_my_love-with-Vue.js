<template>
    <div class="main">
        <section class="showcase">
            <div class="showcase__wrapper container">
                <h2 class="showcase__title">Look at <span class="showcase__title--letter">this</span></h2>
                <blockquote class="showcase__quote">
                    <p class="showcase__quote--text">"It does seem odd that we focus so much of 
                        our attention on this sea of averages, when we should be looking 
                        (as critics do in film and cinema) at the truly outstanding work. 
                        True, there is not that much truely outstanding work, but then neither 
                        is there that much in literature or film."
                    </p><cite class="showcase__quote--author">Colin Pantall's blog</cite>
                </blockquote>
            </div>
        </section>
        <section class="details">
            <div class="details__wrapper container">
                <h3 class="details__title">
                    <q claSS="details__title--text">"I really believe there are things nobody would see if I didn't photograph them."</q>
                    <cite class="details__title--author">Diane Arbus</cite>
                </h3>
                <div class="details__list">
                    <div class="details__item">
                        <img class="details__item--icon" src="../assets/pic1.png" alt="">
                        <div class="details__item--box">
                            <h4 class="details__item--title">Secret of a great picture</h4>
                            <p class="details__item--text">Nothing in this world is entitled to 
                            be a great image. Even the most spectacular events can trigger 
                            nothing if devoid of emotion. Photographers have to experience this 
                            emotion themselves if their viewers are ever going to.*</p>
                        </div>
                    </div>
                     <div class="details__item">
                        <img class="details__item--icon" src="../assets/pic2.png" alt="">
                         <div class="details__item--box">
                            <h4 class="details__item--title">Everything is an emotion</h4>
                            <p class="details__item--text">A world of emotion, experience, 
                            and reality takes place in the time after an image is taken. 
                            A single day, event, moment or even word can change everything in 
                            the time after an image is captured.*</p>
                        </div>
                    </div>
                     <div class="details__item">
                        <img class="details__item--icon" src="../assets/pic3.png" alt="">
                         <div class="details__item--box">
                            <h4 class="details__item--title">Tell me the story</h4>
                            <p class="details__item--text">The more complex and seemingly in-depth
                            an image is, the more difficult it is to truly understand 
                            the feeling of the moment. Some of the most historic images out 
                            there seem to tell us a story, but do they ever really?*</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        <section class="slider">
            <div class="slider__wrapper container">
                Tu będzie slider
                <my-slider :images="images"></my-slider>
            </div>
        </section>
        <!-- *cytaty pochodzą https://www.mimeophotos.com/blog/inspiring-photography-quotes -->
    </div>
</template>

<script>

import MySlider from '../components/MySlider'

export default {
  name: 'Home',
  components: {
      MySlider
  },
  data() {
    return {
       images: [
                {
                    "url": "https://upload.wikimedia.org/wikipedia/commons/8/80/Kwiatek.jpg"
                },

                {
                     "url": "https://upload.wikimedia.org/wikipedia/commons/5/5c/Rosa_villosa_1_MHNT.jpg"
                },

                {
                     "url": "https://upload.wikimedia.org/wikipedia/commons/a/a7/Chamomile%40original_size.jpg"
                }
            ]
    }
  }
}

</script>

<style lang="scss" scoped>

@import "../styles/variables.scss";
@import "../styles/mixins.scss";

    .showcase {
        background-color: $background-top;
        min-height: 70vh;
        background-image: url(../assets/slice1.png);
        background-repeat: no-repeat;
        background-position: right 3rem bottom;

        &__wrapper {
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            align-items: center;
            padding: 5rem 0;
        }

        &__title {
            font-size: 7rem;
            padding-right: 5rem;
            padding-left: 5rem;
            font-weight: bold;

            &--letter {
                color: $alternative-color;
            }
        }

        &__quote {
            padding-left: 5rem;
            padding-right: 5rem;
            text-align: right;

            &--text {
                padding-bottom: 2rem;
                line-height: 1.6;
                font-size: 1.4rem;
            }

            &--author {
                font-size: 1.2rem;
            }
        }
    }

    .details {
        background-color: $background-down;

        &__wrapper {
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            align-items: flex-start;
            padding: 10rem 0 8rem;
        }

         &__title {
            font-size: 2.5rem;
            padding-right: 5rem;
            padding-left: 5rem;
            font-weight: bold;
            display: flex;
            flex-direction: column;

            &--text {
                line-height: 1.3;
                padding-bottom: 1rem;
            }

            &--author {
                font-size: 2rem;
            }
        }

        &__item {

            display: flex;
            flex-direction: row;
            padding-bottom: 3rem;

            &--icon {
                width: 50px;
                height: 52px;
                padding-right: 2rem;
            }

            &--title {
                font-size: 1.5rem;
                font-weight: bold;
                color: $link-color;
                letter-spacing: .8px;
                padding-bottom: 1rem;
            }

            &--text {
                font-size: 1.1rem;
                line-height: 1.3;
            }
        }
    }

    .slider {
        background-color: $background-down;
    }

    .container {
        @include container;
    }


    @media all and (max-width: 768px) {

        .showcase {
            &__title {
                font-size: 3.5rem;
                padding-right: 1.5rem;
                padding-left: 3rem;
            }

            &__quote {
                padding-left: 1.5rem;
                padding-right: 3rem;

                &--text {
                    font-size: 1rem;
                }
            }
        }
    }

    @media all and (max-width: 480px) {
        .showcase {

            &__wrapper {
               flex-direction: column;
               padding-top: 4rem;
            }
            &__title {
                font-size: 3rem;
                padding-left: 2rem;
                padding-bottom: 2rem;
            }

            &__quote {
                padding-right: 3rem;
                &--text {
                    font-size: 1rem;
                }
            }
        }
    }

</style>
