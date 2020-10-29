<template>
    <section class="team">
       <div class="team__wrapper container">
           <h2 class="team__title">My favorite team</h2>
                <div class="team__box">
               <!-- <div class="team__card">
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
               </div> -->
               <team-card :obverse="obverse" @otherView="secondView" v-for="person in team" v-bind:person="person" :key="person.name"></team-card>
                
                </div>
       </div>
    </section>
</template>

<script>

import TeamCard from './TeamCard';

export default {
    name: 'my-team',
    components: {
        TeamCard
    },
    data() {
        return {
            obverse: true,
            team: [
                {
                    name: 'Maria Ciuri',
                    profession: 'web designer',
                    words: 'My beloved Vue.js' 
                },
                {
                    name: 'Ron Johnson',
                    profession: 'web developer',
                    words: 'Vue.js is my big love' 
                },
                 {
                    name: 'Graham Pitt',
                    profession: 'CTO',
                    words: 'Great Vue.js forever!' 
                },
            ]
        }
    },
    methods: {
        secondView(value) {
            this.obverse = value;
        }
    }
}
</script>

<style lang="scss" scoped>

@import "../styles/variables.scss";
@import "../styles/mixins.scss";

.team {
    background-color: $link-color;
    color: $background-top;

    &__wrapper {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    &__title {
        font-size: 3rem;
        font-weight: bold;
        padding: 5rem 2rem;
    }
}

.container {
    @include container;
}

</style>