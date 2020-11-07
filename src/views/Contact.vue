<template>
    <div class="contact">
        <section class="contact__contact">
            <div class="contact__wrapper container">
                <h2 class="contact__title">Please contact us...</h2>
                <h3 class="contact__subtitle">We are always happy to find out what's on your mind</h3>
                <my-form></my-form>
            </div>
        </section>
        <my-footer>
            The inspiration comes from Frontend Mentor.<br/>
        </my-footer>        
    </div>
</template>

<script>

import MyForm from '../components/MyForm'
import MyFooter from '../components/MyFooter'

export default {
    name: 'Contact',
    components: {
        MyForm,
        MyFooter, 
    }
}
</script>

<style lang="scss" scoped>

@import "../styles/variables.scss";
@import "../styles/mixins.scss";

.contact {

    &__contact {
        background-color: $background-top;
        padding-top: 7rem;
        padding-bottom: 4rem;
    }

    &__wrapper {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        line-height: 1.4;
    }

    &__title {
        font-size: 3rem;
        font-weight: bold;
        padding: 0 2rem 2rem;
        color: $link-color;
    }

     &__subtitle {
        font-size: 1.8rem;
        // font-weight: bold;
        padding: 0 2rem 4rem;
        color: $link-color;
    }
}

@media all and (max-width: 768px) {
    .contact__title {
        font-size: 2rem;
    }

    .contact__subtitle {
        font-size: 1.5rem;
        padding-bottom: 2rem;
    }
}


</style>