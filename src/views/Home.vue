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
                        <img class="details__item--icon" src="../assets/pic1.png" alt="picture irrelevent">
                        <div class="details__item--box">
                            <h4 class="details__item--title">Secret of a great picture</h4>
                            <p class="details__item--text">Nothing in this world is entitled to 
                            be a great image. Even the most spectacular events can trigger 
                            nothing if devoid of emotion. Photographers have to experience this 
                            emotion themselves if their viewers are ever going to.*</p>
                        </div>
                    </div>
                     <div class="details__item">
                        <img class="details__item--icon" src="../assets/pic2.png" alt="picture irrelevent">
                         <div class="details__item--box">
                            <h4 class="details__item--title">Everything is an emotion</h4>
                            <p class="details__item--text">A world of emotion, experience, 
                            and reality takes place in the time after an image is taken. 
                            A single day, event, moment or even word can change everything in 
                            the time after an image is captured.*</p>
                        </div>
                    </div>
                     <div class="details__item">
                        <img class="details__item--icon" src="../assets/pic3.png" alt="picture irrelevent">
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
             
                <my-slider :images="images"></my-slider>
      
            </div>
        </section>
        <section class="reference">
            <div class="reference__wrapper container">
                <h2 class="reference__title">Happy Customers</h2>
                <h3 class="reference__subtitle">some of my best clients</h3>
                <div class="reference__list">
                    <div class="reference__item">
                        <img class="reference__item--photo" :src="whereIsAphoto(photo[0])" alt="photo of author"/>
                        <h3 class="reference__item--name">Alicia Coconut</h3>
                        <h4 class="reference__item--role">CEO of Portage</h4>
                        <p class="reference__item--cite">"Cooperation with
                             this brand was very fruitful. The artist's passion 
                             was felt by us throughout the entire period.
                            The author puts her whole heart into the joint venture."</p>
                    </div>
                    <div class="reference__item">
                        <img class="reference__item--photo" :src="whereIsAphoto(photo[1])" alt="photo of author"/>
                        <h3 class="reference__item--name">Alicia Coconut</h3>
                        <h4 class="reference__item--role">CEO of Portage</h4>
                        <p class="reference__item--cite">"Cooperation with
                             this brand was very fruitful. The artist's passion 
                             was felt by us throughout the entire period.
                            The author puts her whole heart into the joint venture."</p>
                    </div>
                    <div class="reference__item">
                        <img class="reference__item--photo" :src="whereIsAphoto(photo[2])" alt="photo of author"/>
                        <h3 class="reference__item--name">Alicia Coconut</h3>
                        <h4 class="reference__item--role">CEO of Portage</h4>
                        <p class="reference__item--cite">"Cooperation with
                             this brand was very fruitful. The artist's passion 
                             was felt by us throughout the entire period.
                            The author puts her whole heart into the joint venture."</p>
                    </div>
                </div>
            </div>
           
        </section>
        <!-- *cytaty pochodzą https://www.mimeophotos.com/blog/inspiring-photography-quotes -->
        <!-- zdjecia klietów pochodzą z unsplash -->
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
                "url" : "/photo1.jpg"
            },

            {
                "url" : "/photo2.jpg"
            },

            {
                "url" : "/photo3.jpg"
            },

            {
                "url" : "/photo3.jpg"
            },

            {
                "url" : "/photo4.jpg"
            },

            {
                "url" : "/photo5.jpg"
            }
        ],
        photo: [
            "/client1.png",
            "/client2.png",
            "/client3.png"
        ]
    }
  },

  methods: {
      whereIsAphoto(image) {
          return require('../assets/photo' + image);
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

        &__list {
            padding-right: 5rem;
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
        background-color: $background-top; 

        &__wrapper {
            width: 100%;
            padding: 3rem 0;
        }
    }

    .reference {
        background-color: $alternative-color;

        &__wrapper {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 6rem 1rem 4rem;
        }

        &__title {
           font-size: 3rem;
           font-weight: bold;
           padding-bottom: 1.2rem;
        }

        &__subtitle {
            font-size: 2rem;
            font-weight: bold;
            letter-spacing: 1px;
        }

        &__list {
            display: flex;
            flex-direction: row;
            justify-content: space-around;
            align-items: center;
            padding: 4rem 0;
        }

        &__item {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 1rem;
            margin: 0 .5rem;
            background-color: $background-down;
            padding: 2rem 1rem;
            box-shadow: 0 15px 6px -6px #242000;
            cursor: pointer;
            transition: all .3s ease;

            &:hover {
                transform: scale(1.1);
            }

            &--photo {
                width: 6rem;
                height: 6rem;
                border-radius: 50%;
                border: 5px solid $background-top;
            }
            
            &--name {
                font-size: 1.3rem;
                padding: 1rem .5rem .5rem;
            }

            &--role {
                font-size: 1rem;
            }

            &--cite {
                font-size: .9rem;
                padding: 2rem 1rem;
                line-height: 1.6;
                text-align: center;
            }
        }


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

        .details {

            &__wrapper {
                flex-direction: column;
                align-items: center;
                padding-top: 8rem;
                padding-bottom: 4rem;
            }

            &__title {
                align-self: center;
                padding-bottom: 4rem;
            }

            &__list {
                align-self: center;
                display: flex;
                flex-direction: column;
                justify-content: center;
                padding: 2rem;
            }
        }

        .reference {

            &__wrapper {
                padding: 3rem 2rem .5rem;
            }

            &__list {
                flex-direction: column;
            }

            &__item {
                margin-bottom: 2rem;

                &:hover {
                    transform: scale(1);
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

        .details {

            &__wrapper {
                padding-top: 4rem;
                padding-bottom: 2rem;
            }

            &__title {
                font-size: 1.8rem;
                padding: 0 2rem 2rem;
            }

            &__item {

                &--icon {
                    padding-right: 1rem;
                }

                &--title {
                    font-size: 1.2rem;
                }

                &--text {
                    font-size: .8rem;
                    line-height: 1.6;
                }
            }
        }
    }

</style>
