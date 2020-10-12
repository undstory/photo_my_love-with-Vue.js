<template>
    <div class="mobile__menu" v-if="visible">
        <button class="mobile__close--btn"><i class="fas fa-times"></i></button>
        <nav class="mobile__nav">
            <router-link to="/" class="mobile__link">Home</router-link>
            <router-link to="/about" class="mobile__link">About</router-link>
            <router-link to="/contact" class="mobile__link">Contact</router-link>
        </nav>
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
        text-align: right;
        border: 1px solid red;
    }

    .mobile__nav {
        display: flex;
        flex-direction: column;
    }

    .mobile__link {
        color:  $font-color;
    }

</style>