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
                    words: 'I am inspired by my world.',
                    obverse: true,
                },
                {
                    name: 'Ron Johnson',
                    profession: 'web developer',
                    words: 'Vue.js is my greatest love.', 
                    obverse: true,
                },
                {
                    name: 'Graham Pitt',
                    profession: 'CTO',
                    words: 'Learning and development forever!',
                    obverse: true,
                },
                 {
                    name: 'Jane Isuppose',
                    profession: 'illustrator',
                    words: 'Be yourself always and everywhere!',
                    obverse: true,
                },
                 {
                    name: 'Eva Van Der Holt',
                    profession: 'Photoshop master',
                    words: 'Still being creative.',
                    obverse: true,
                },
                 {
                    name: 'Chris Neverland',
                    profession: 'web developer',
                    words: 'I keep trying and never gives up.',
                    obverse: true,
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
        padding: 0 2rem 8rem;
    }
}

.container {
    @include container;
}

</style>