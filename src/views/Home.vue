<template>
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
</template>

<script>

export default {
  name: 'Home',
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
        // width: 30px;
        // height: 20px;

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

    .container {
        @include container;
    }


</style>
