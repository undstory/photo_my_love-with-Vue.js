<template>
    <div class="about">
        <section class="about__about">
            <div class="about__wrapper container">
                <div class="about__description">
                    <h2 class="about__description--title">Behind the scene</h2>
                    <img src="../assets/me.png" class="about__img2" alt="picture of author">

                    <h3 class="about__description--subtitle">Hello!</h3>
                    <p class="about__description--text">I'm Poland based freelance front-end developer, web designer, collage enthusiast.</p>
                    <p class="about__description--text">I am passionate about art, especially in the areas of graphics, illustration and photography.
                    I work as a front end developer, especially with the Vue.js framework, I also deal with web design.
                    However, my greatest love is illustration in the collage technique.
                    I love looking for interesting combinations of colors and forms - 
                    it opens the mind to other directions of artistic measures.</p>
                    <p class="about__description--text">Usually I collaborate with fashion brands, cultural institutions, publishers and agencies 
                    based in Poland and abroad. Sometimes I created for Individuals also.</p> 
                </div>
                <img src="../assets/me.png" class="about__img" alt="picture of author">
            </div>
        </section>
        <my-team></my-team>
        <my-footer></my-footer>
    </div>
</template>

<script>

import MyFooter from '../components/MyFooter'
import MyTeam from '../components/Myteam'

export default {
    name: 'About',
    components: {
      MyFooter,
      MyTeam
  },
}
</script>

<style lang="scss" scoped>

@import "../styles/variables.scss";
@import "../styles/mixins.scss";

    .about {
        &__about {
            background-color: $background-top;
            min-height: 70vh;
            padding-top: 5rem;
        }

        &__wrapper {
            display: flex;
            flex-direction: row;
            justify-content: center;
            align-items: center;
        }

        &__img {
            max-width: 40%;
            max-height: 40%;
            padding: 0 2rem;
        }

        &__img2 {
            display: none;
        }

        &__description {
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            padding-left: 3rem;

            &--title {
                font-size: 2.5rem;
                font-weight: bold;
                padding-bottom: 4rem;
                color: $link-color;
            }

            &--subtitle {
                font-size: 1.7rem;
                padding-bottom: 2rem;
            }

            &--text {
                font-size: 1.2rem;
                padding-bottom: 1.5rem;
                line-height: 1.4;
                padding-right: 2rem;
            }
        }
    }

    @media all and (max-width: 1200px) {
        .about__description {
            &--text {
                font-size: 1rem;
            }
        }

        .about__wrapper {
            align-items: flex-start;
        }
    }

    @media all and (max-width: 768px) {

        .about__img {
            display: none;
        }

        .about__img2 {
            display: inline-block;
            width: 60%;
            align-self: flex-end;
            padding-right: 2rem;
        }

        .about__description--title {
            padding-bottom: 2rem;
        }
    }

    @media all and (max-width: 480px) {

        .about {
            &__about {
                padding-top: 3rem;
            }

            &__description {
                padding-left: 2rem;
            }

            &__img2 {
                display: none;
            }
        }
    }

</style>
