<template>
    <div>
        
        <div class="team__card" >
                    <transition mode="out-in">
                    <div class="card team__card--obverse" v-if="look" key="0">
                            <img class="card__img" src="" alt="">
                            <h3 class="card__name">{{ person.name }}</h3>
                            <h4 class="card__profession">{{ person.profession }}</h4>
                    </div>
                     
                    <div class="team__card--reverse" v-else key="">
                            <h3 class="card__name">{{ person.name }}</h3>
                            <p class="card__words">{{ person.words}}</p>
                            <div class="card__social">
                                <a class="card__social--link"><i class="fab fa-instagram-square"></i></a>
                                <a class="card__social--link"><i class="fab fa-facebook-square"></i></a>
                            </div>
                    </div>
                    </transition>
           
                    <button class="team__card--btn" @click="changeView">More...</button>

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
        padding: 3rem 2rem;
        position: relative;
        border-radius: 10px;
        border: 3px solid $background-down;
        background-color: lighten($link-color, 8);

        &--btn {
            position: absolute;
            bottom: -1.2rem;
            padding: .3rem 1rem;
            border: 3px solid $background-down;
            background-color: $link-color;
            font-size: 1.1rem;
            text-transform:lowercase;
            cursor: pointer;
            outline: none;

            &:hover {
                background-color: $background-down;
                color: $font-color;
            }
        }
    }
}

.v-enter-active, .v-leave-active {
    transition: opacity .5s;
}

.v-enter, .v-leave-to {
    opacity: 0;
}




</style>