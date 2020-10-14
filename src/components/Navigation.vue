<template>

    <div class="nav">
        <div class="container">
            <div class="nav__main">
                <div class="nav__logo"><router-link to="/" class="nav__logo">photoMyLove</router-link></div>
                <nav class="nav__menu">
                    <router-link to="/" class="nav__link">Home</router-link>
                    <router-link to="/about" class="nav__link">About</router-link>
                </nav>
            </div>
            <button class="nav__contact"><router-link to="/contact" class="nav__contact--link">Contact</router-link></button>
            <button class="nav__mobile--btn" @click="$root.$emit('toggleMenu')"><i class="fas fa-bars"></i></button>
        </div>
        <mobile-menu></mobile-menu>
    </div>

</template>

<script>

import MobileMenu from './MobileMenu'

export default {
    name: 'Navi',
    components: {
        MobileMenu
    },
}
</script>

<style lang="scss" scoped>

@import "../styles/variables.scss";
@import "../styles/mixins.scss";

    .nav {
        padding: 3rem 1.5rem 2.5rem;
        background-color: $background-top;
        color: $font-color;
    }

    .container {
        @include container;
        display: flex;
        justify-content: space-between;
        align-items: baseline;
    }

    .nav__main {
        display: flex;
        flex-direction: row;
        align-items: flex-end;
    }

    .nav__link {
        color: $font-color;
        text-decoration: none;
        padding: 0 2rem 0 1rem;

        &:hover {
            color: $link-color;
        }
    }

    .nav__menu {
        font-size: 1.4rem;
        text-transform: lowercase;
    }

    .nav__logo {
        color: $font-color;
        text-decoration: none;
        padding-right: 3rem;
        // font-weight: bold;
        font-size: 2.8rem;
    }

    .nav__contact {
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

    .nav__mobile--btn {
        outline: none;
        border: none;
        cursor: pointer;
        background-color: transparent;

        i {
            color: $font-color;
            font-size: 2.2rem;
        }
    }

    .nav__mobile--btn {
        display: none;
    }

    @media all and (max-width: 768px) {

        .nav__menu, .nav__contact {
            display: none;
        }

        .nav__mobile--btn {
            display: block;
        } 
    }

     @media all and (max-width: 480px) {

        .nav {
             padding-right: .8rem;
             padding-left: .8rem;
        }
        .nav__logo {
             font-size: 2rem;
             padding-right: 1rem;
        }
    }
</style>