<template>
    <section class="team">
       <div class="team__wrapper container">
           <h2 class="team__title">My favorite team</h2>
           <div class="team__box">
               <div class="team__card">
                   <div class="card team__card--obverse">
                        <img class="card__img" src="" alt="">
                        <h3 class="card__name">Lucy LaBelle</h3>
                        <h4 class="card__profession">Graphic Designer</h4>
                   </div>
                   <div class="team__card--reverse">
                        <h3 class="card__name">Lucy LaBelle</h3>
                        <p class="card__words">The definition of happiness? When a beloved passion becomes work.</p>
                        <div class="card__social">
                            <a class="card__social--link"><i class="fab fa-instagram-square"></i></a>
                            <a class="card__social--link"><i class="fab fa-facebook-square"></i></a>
                        </div>
                   </div>
                   <button class="team__card--btn">Details</button>
               </div>
           </div>
       </div>
    </section>
</template>

<script>
export default {
    name: 'my-team'
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
        display: flex; 
        flex-direction: row;
    }

    // &__card {
    //     display: flex;
    //     flex-direction: column;
    //     justify-content: center;
    //     align-items: center;
    // }
}

.container {
    @include container;
}

</style>