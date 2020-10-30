<template>
    <div>
        <div class="team__card" >
                    <div class="card team__card--obverse" v-if="look">
                            <img class="card__img" src="" alt="">
                            <h3 class="card__name">{{ person.name }}</h3>
                            <h4 class="card__profession">{{ person.profession }}</h4>
                    </div>
                    <div class="team__card--reverse" v-else>
                            <h3 class="card__name">{{ person.name }}</h3>
                            <p class="card__words">{{ person.words}}</p>
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
        person: {
            type: Object,
            required: true
        }
    },
    data() {
        return {
            name: this.person.name,
            profession: this.person.profession,
            words: this.person.words,
            obverse: this.person.obverse     
        }
    },
    computed: {
        look() {
            if(this.obverse === true) {
                return true;
            }
            return false;
        }
    },
    methods: {
        changeView() {
            this.obverse = !this.obverse;
            this.$emit("otherView", {
                'person': {
                    obverse: this.obverse   
                }
            })
        }
    }
}
</script>


<style lang="scss" scoped>

@import "../styles/variables.scss";
@import "../styles/mixins.scss";

.team {
    &__card {
        display: flex;
        flex-direction: column;
        align-items: center;
        border: 1px solid red;
        margin: 0 3%;
        padding: 2rem
    }
}


</style>