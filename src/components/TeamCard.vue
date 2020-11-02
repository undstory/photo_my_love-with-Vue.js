<template>
    <div>
        
        <div class="team__card" >
                    <transition mode="out-in">
                    <div class="card team__card--obverse" v-if="look" key="0">
                            <img class="card__img" :src="image(person.photo)" alt="photo of a group member">
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
           
                    <button class="team__card--btn" @click="changeView">+</button>

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
            obverse: this.person.obverse,
            photo: this.person.photo     
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
        },

        image(im) {
            return require('../assets/photo' + im);
        },
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
        justify-content: center;
        text-align: center;
        padding: 2rem;
        position: relative;
        border-radius: 10px;
        border: 5px solid $background-down;
        background-color: lighten($link-color, 8);
        height: 150px;

        &--btn {
            position: absolute;
            bottom: -1.2rem;
            padding: .3rem 1rem;
            border: 3px solid $background-down;
            background-color: $background-down;
            font-size: 1.1rem;
            text-transform:lowercase;
            cursor: pointer;
            outline: none;
            color: $font-color;
            font-weight: bold;

            &:hover {
                font-weight: bold;
                color: $background-down;
                background-color: $link-color;
            }
        }
    }
}

.card {
    &__img {
        width: 100px;
        height: 100px;
        border-radius: 50%;
        border: 5px solid $background-top;
    }

    &__name {
        font-size: 1.2rem;
        font-weight: bold;
        margin: .5rem 0;
    }

    &__profession {
        font-size: 1rem;
        margin: .5rem 0 .8rem;
    }

    &__words {
        font-size: 1.2rem;
        margin: .9rem 0;
    }

    &__social {
        margin: 1rem 0;

        &--link {
            cursor: pointer;
            font-size: 1.8rem;
            margin: 0 .5rem 0;

            &:hover {
                color: $background-down;
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

@media all and (max-width: 560px) {
    .team__card {
        margin-top: 2.5rem;
    }
}

</style>