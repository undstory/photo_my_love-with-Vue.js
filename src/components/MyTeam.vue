<template>
    <section class="team">
       <div class="team__wrapper container">
           <h2 class="team__title">My favorite team about myself</h2>
                <div class="team__box">
    
                    <team-card  @otherView="otherView" v-for="person in team" v-bind:person="person" :key="person.name"></team-card>
                
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
           
            team: [
                {
                    name: 'Maria Ciuri',
                    profession: 'web designer',
                    words: '"I am inspired by my world."',
                    obverse: true,
                    photo: "/teamF.jpg"
                },
                {
                    name: 'Ron Johnson',
                    profession: 'web developer',
                    words: '"Vue.js is my greatest love."', 
                    obverse: true,
                    photo: "/teamM.jpg"
                },
                {
                    name: 'Graham Pitt',
                    profession: 'CTO',
                    words: '"Learning and development forever!"',
                    obverse: true,
                    photo: "/teamM2.jpg"
                },
                 {
                    name: 'Jane Isuppose',
                    profession: 'illustrator',
                    words: '"Be yourself always and everywhere!"',
                    obverse: true,
                    photo: "/teamF2.jpg"
                },
                 {
                    name: 'Eva Van Der Holt',
                    profession: 'Photoshop master',
                    words: '"Still being creative."',
                    obverse: true,
                    photo: "/teamF3.jpg"
                },
                 {
                    name: 'Chris Neverland',
                    profession: 'web developer',
                    words: '"I keep trying and never gives up."',
                    obverse: true,
                    photo: "/teamM3.jpg"
                },
            ]
        }
    },
    methods: {
            otherView(value) {
                this.team.obverse = value;
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
    padding-bottom: 12rem;

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

    &__box {
        display: grid;
        grid-template-columns: 27% 27% 27%;
        grid-template-rows: 30% 30%;
        grid-row-gap: 50%;
        grid-column-gap: 5%;
        justify-content: center;
        width: 100%;
        padding: 0 0 8rem;
    }
}

.container {
    @include container;
}

@media all and (max-width: 768px) {
    .team {

        padding-bottom: 18rem;

        &__box {
            grid-template-columns: 35% 35%;
            grid-template-rows: .5% .5% .5%;
            padding-bottom: 3rem;
        }
     
    }
}

@media all and (max-width: 560px) {
    .team {

        padding-bottom: 5rem;

            &__title {
                padding-bottom: 3rem;
            }

           &__box {
            display: flex;
            flex-direction: column;
            justify-content: center;
            width: 70%;
            padding-bottom: 1rem;
    }
}
}

</style>