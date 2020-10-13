<template>
    <div class="mobile__menu--wrapper">
        <div class="mobile__menu" v-if="visible">
            <button class="mobile__close--btn"><i class="fas fa-times"></i></button>
            <nav class="mobile__nav">
                <router-link to="/" class="mobile__link">Home</router-link>
                <router-link to="/about" class="mobile__link">About</router-link>
                <router-link to="/contact" class="mobile__link">Contact</router-link>
            </nav>
        </div>
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
        border: 1px solid red;
        position: fixed;
        top: 0;
        right: 0;
        width: 50%;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        text-align: right;
        padding: 2rem 2rem 0 0;
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
    }

    .mobile__close--btn {
        @include btn;
        i {
            font-size: 1.5rem;
            color: $font-color;
        }
    }

</style>