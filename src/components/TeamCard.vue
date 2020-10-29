<template>
    <div>
        <div class="team__card" >
                    <div class="card team__card--obverse" v-if="obverse">
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
                   
        </div>
         <button class="team__card--btn" @click="changeView">Details</button>
 </div>
    
</template>

<script>
export default {
    name: 'team-card',
    props: {
        obverse: {
            type: Boolean,
            required: true
        },
        person: {
            type: Object,
            required: true
        }
    },
    data() {
        return {
            view: this.obverse,
            name: this.person.name,
            profession: this.person.profession,
            words: this.person.words        
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


<style lang="scss" scoped>

@import "../styles/variables.scss";
@import "../styles/mixins.scss";


</style>