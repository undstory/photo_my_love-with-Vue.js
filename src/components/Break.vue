<template>
    <div class="break">
            <div class="break__wrapper container">
                <h2 class="break__slogan">What are you waiting for?</h2>
                <button class="break__contact"><router-link to="/contact" class="break__contact--link">Contact</router-link></button>
            </div>    
        </div>
</template>

<script>
export default {
    name: 'Break'
}
</script>


<style lang="scss" scoped>

@import "../styles/variables.scss";
@import "../styles/mixins.scss";

.break {
        background-color: $background-top;
        background-image: url(../assets/slice1.png);
        background-repeat: no-repeat;
        background-position: right 50% bottom;
        background-size: 200px 100px;

        &__wrapper {
            display: flex;
            justify-content: space-between;
            padding: 6rem 2rem;
        }

        &__slogan {
            font-size: 2.5rem;
            font-weight: bold;
            padding-left: 2rem;
        }

        &__contact {
        @include btn;

        &:hover {
            background-color: $link-color;
        }

        &--link {
            text-decoration: none;
            color: $font-color;
            text-transform: uppercase;
            font-size: 1rem;
            letter-spacing: 1px;

            &:hover {
            color: $background-top;
            font-weight: bold;
            }
        }
    }
    }

    .container {
        @include container;
    }

     @media all and (max-width: 768px) {

        .break {
            background-position: left bottom;

            &__wrapper {
                flex-direction: column;
                align-items: center;
            }

            &__slogan {
                padding-bottom: 2rem;
                text-align: center;
            }
        }
    }

    @media all and (max-width: 480px) {

        .break {
            background-size: 200px 100px;

            &__slogan {
                padding: 1rem 2rem;
                font-size: 2rem;
                line-height: 1.4;
            }

            &__wrapper {
                padding-top: 3rem;
                
            }

            &__contact {
                margin-bottom: 1rem;
            }
        }
    }


</style>