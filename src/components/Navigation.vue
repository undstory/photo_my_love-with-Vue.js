<template>

    <div class="nav">
        <div class="container">
            <div class="nav__main">
                <div class="nav__logo"><router-link to="/" class="nav__logo">photo_my_love</router-link></div>
                <nav class="nav__menu">
                    <router-link to="/" class="nav__link">Home</router-link>
                    <router-link to="/about" class="nav__link">About</router-link>
                </nav>
            </div>
           
           <button class="nav__contact"><router-link to="/contact" class="nav__contact--link">Contact</router-link></button>
        
        </div>
     
   
    </div>
</template>

<script>

export default {
    name: 'Navi'
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
        border: 2px solid $font-color;
        border-radius:  15px;
        background-color: transparent;
        padding: .8rem 1.5rem;

        &--link {
            text-decoration: none;
            color: $font-color;
            text-transform: uppercase;
            font-size: 1rem;
            letter-spacing: 1px;
        }
    }
</style>