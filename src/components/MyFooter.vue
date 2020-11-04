<template>
    <footer class="footer">
        <div class="footer__wrapper container">
            <div class="footer__top">
                <h2 class="footer__logo"><router-link to="/" class="footer__logo">photoMyLove</router-link></h2>
                <ul class="footer__social">
                    <li><a class="footer__social--link"><i class="fab fa-facebook"></i></a></li>
                    <li><a class="footer__social--link"><i class="fab fa-instagram-square"></i></a></li>
                    <li><a class="footer__social--link"><i class="fab fa-behance-square"></i></a></li>
                    <li><a class="footer__social--link"><i class="fab fa-dribbble-square"></i></a></li>
                </ul>
            </div>
            <div class="footer__down">
                <div class="footer__menu">
                    <router-link to="/" class="footer__link">Home</router-link>
                    <router-link to="/about" class="footer__link">About</router-link>
                </div>
                <div class="footer__copy">Design & Code & Photo from gallery - 
                    all created by Undstory, 2020.<br />
                    <slot></slot>
                    Customer photos are taken from unsplash.
                </div>
           </div>
        </div>
    </footer>
</template>

<script>
export default {
    name: 'my-footer'
}
</script>

<style lang="scss" scoped>

@import "../styles/variables.scss";
@import "../styles/mixins.scss";

.footer {
    background-color: $link-color;
    color: $background-top;
    padding: 5rem 2rem;

    &__top {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }

    &__social {
        display: flex;
        flex-direction: row;

        &--link {
            font-size: 2.5rem;
            padding-left: 1.5rem;
            cursor: pointer;

            &:hover {
                color: $background-down;
            }
        }
    }

    &__logo {
        color: $font-color;
        text-decoration: none;
        padding-right: 3rem;
        font-weight: bold;
        font-size: 2.8rem;
        color: $background-top;
    }

    &__down {
        padding-top: 4rem;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }

    &__menu {
        font-size: 1.4rem;
        text-transform: lowercase;
    }

    &__link {
        text-decoration: none;
        padding: 2rem 1rem;
        color: $background-top;
        font-weight: bold;

        &:hover {
            color: $background-down;
        }
    } 

    &__copy {
        text-align: right;
        line-height: 1.4;
    }
}

.container {
    @include container;
}

@media all and (max-width: 768px) {
    .footer {
        &__down, &__top {
            flex-direction: column;
        }

        &__down {
            padding-top: 1rem;
        }

        &__logo {
            padding-bottom: 2rem;
        }

        &__menu {
            display: none;
        }

        &__copy {
            text-align: left;
            padding-top: 2rem;
        }

        &__logo {
            font-size: 2rem;
            padding-right: 2rem;
        }

        &__social--link {
            padding: 0 1rem;
        }
    }
}
</style>