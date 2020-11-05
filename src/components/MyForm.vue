<template>
    <form action="#" class="form">
        <input type="text" class="form__input field" name="firstName" placeholder="First name" required/>
        <input type="text" class="form__input field" name="lastName" placeholder="Last name" required/>
        <input type="text" class="form__input field" name="company" placeholder="Company name" required/>
        <input type="email" class="form__input field" name="email" placeholder="E-mail" required/>
        <textarea class="form__textarea field" name="message" maxlength="500" placeholder="Message" style="font-family: 'Hind Siliguri'" required></textarea>
        <button type="submit" class="form__btn field">Send</button>
    </form>
</template>

<script>
export default {
    name: "MyForm"
}
</script>

<style lang="scss" scoped>

@import "../styles/variables.scss";
@import "../styles/mixins.scss";

.field {
    font-size: 1.3rem;
    margin-bottom: 2rem;
    background-color: $font-color;
    outline: 5px solid $background-down; 
    border: none;
    color: $background-down;
    padding: 0 1rem;
}

.form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;

    &__input {
        width: 40%;
        height: 2.8rem;
        
    }

    &__btn {
        padding: 1rem 2rem;
        background-color: $background-down;
        color: $font-color;
        font-weight: bold;
        letter-spacing: 1px;

        &:hover {
            background-color: $link-color;
            color: $background-top;
        }
    }

    &__textarea {
        padding-top: 1rem;
        padding-bottom: 1rem;
        width: 40%;
        height: 10rem;
    }
}



</style>