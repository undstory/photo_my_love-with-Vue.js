<template>
    <div>
        <div class="team__card">
                    <div class="card team__card--obverse" v-if="obverse">
                            <img class="card__img" src="" alt="">
                            <h3 class="card__name">Lucy LaBelle</h3>
                            <h4 class="card__profession">Graphic Designer</h4>
                    </div>
                    <div class="team__card--reverse" v-else>
                            <h3 class="card__name">Lucy LaBelle</h3>
                            <p class="card__words">The definition of happiness? When a beloved passion becomes work.</p>
                            <div class="card__social">
                                <a class="card__social--link"><i class="fab fa-instagram-square"></i></a>
                                <a class="card__social--link"><i class="fab fa-facebook-square"></i></a>
                            </div>
                    </div>
                    <button class="team__card--btn" @click="changeView">Details</button>
        </div>
        <div class="team__card">
                    <div class="card team__card--obverse" v-if="obverse">
                            <img class="card__img" src="" alt="">
                            <h3 class="card__name">Lucy LaBelle</h3>
                            <h4 class="card__profession">Graphic Designer</h4>
                    </div>
                    <div class="team__card--reverse" v-else>
                            <h3 class="card__name">Lucy LaBelle</h3>
                            <p class="card__words">The definition of happiness? When a beloved passion becomes work.</p>
                            <div class="card__social">
                                <a class="card__social--link"><i class="fab fa-instagram-square"></i></a>
                                <a class="card__social--link"><i class="fab fa-facebook-square"></i></a>
                            </div>
                    </div>
                    <button class="team__card--btn" @click="changeView">Details</button>
        </div>
        <div class="team__card">
                    <div class="card team__card--obverse" v-if="obverse">
                            <img class="card__img" src="" alt="">
                            <h3 class="card__name">Lucy LaBelle</h3>
                            <h4 class="card__profession">Graphic Designer</h4>
                    </div>
                    <div class="team__card--reverse" v-else>
                            <h3 class="card__name">Lucy LaBelle</h3>
                            <p class="card__words">The definition of happiness? When a beloved passion becomes work.</p>
                            <div class="card__social">
                                <a class="card__social--link"><i class="fab fa-instagram-square"></i></a>
                                <a class="card__social--link"><i class="fab fa-facebook-square"></i></a>
                            </div>
                    </div>
                    <button class="team__card--btn" @click="changeView">Details</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'team-card',
    props: {
        obverse: {
            type: Boolean,
            required: true
        }
    },
    data() {
        return {
            view: this.obverse
        }
    },
    methods: {
        changeView() {
            this.view = !this.view;
            this.$emit("otherView", 
                this.view
            
           )
            
        }
    }
}
</script>

<style>

</style>