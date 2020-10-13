<template>

    <div class="mobile__menu--wrapper">
        <transition name="mobile__menu--transition">
            <div class="mobile__menu" v-if="visible">
                <button class="mobile__close--btn" @click="visible = false"><i class="fas fa-times"></i></button>
                <nav class="mobile__nav">
                    <router-link to="/" class="mobile__link" @click.native="visible = false">Home</router-link>
                    <router-link to="/about" class="mobile__link" @click.native="visible = false">About</router-link>
                    <router-link to="/contact" class="mobile__link" @click.native="visible = false">Contact</router-link>
                </nav>
            </div>
        </transition>
    </div>
   
</template>

<script>

export default {
    name: 'MobileMenu',
    data() {
        return {
            visible: false
        }
    },
    created() {
        this.$root.$on('toggleMenu', () => {
            this.visible = !this.visible;
        })
    }
}
</script>

<style lang="scss" scoped>

@import "../styles/variables.scss";
@import "../styles/mixins.scss";

    .mobile__menu {
        background-color: $background-top;
        position: fixed;
        top: 0;
        right: 0;
        width: 50%;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        text-align: right;
        padding: 3rem 2rem 0 0;
    }

    .mobile__nav {
        font-size: 2rem;
        display: flex;
        flex-direction: column;
        padding-top: 2rem;
    }

    .mobile__link {
        color:  $font-color;
        text-decoration: none;
        padding-bottom: 1.5rem;
        text-transform: lowercase;

        &:hover {
            color: $link-color;
        }
    }

    .mobile__close--btn {

        @include btn;

        &:hover {
            background-color: $link-color;
        }

        i {
            font-size: 1.5rem;
            color: $font-color;

            &:hover {
                color: $background-top;
                font-weight: bold;
            }
        }
    }

    .mobile__menu--transition {
       
        &-enter-active {
            transition: transform 0.3s ease;
        }

    //ukryj - opacity 0
        &-enter {
            transform: translateX(100%);
        }

    // pokaz - opacity 1
        &-enter-to { 
            transform: translateX(0%);
        }

        &-leave-active {
            transition: transform 0.3s ease;
        }

    //ukryj - opacity 0
        &-leave-to {
            transform: translateX(100%)
        }

    //pokaz - opacity 1 
        &-leave {
            transform: translateX(0%);
        }
    }

    @media all and (max-width: 480px) {
        .mobile__menu {
            width: 100%;
        }
    }

</style>