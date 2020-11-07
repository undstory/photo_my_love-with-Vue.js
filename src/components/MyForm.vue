<template>
    <form action="#" class="form" @submit.prevent novalidate>
       
        <input type="text" class="form__input field" name="firstName" v-model="firstName" placeholder="First name" @input="$v.firstName.$touch()" :class="{'errors': $v.firstName.$error}" autofocus />
        <p v-if="$v.firstName.$dirty && !$v.firstName.required">This field is required</p>
        <p v-if="$v.firstName.$dirty && !$v.firstName.minLength">At least two characters are required</p>
        <p v-if="$v.firstName.$dirty && !$v.firstName.alpha">Only letters are accepted</p>
     
       
        <input type="text" class="form__input field" name="lastName" v-model="lastName" placeholder="Last name"  @input="$v.lastName.$touch()" :class="{'errors': $v.lastName.$error}" />
        <p v-if="$v.lastName.$dirty && !$v.lastName.required">This field is required</p>
        <p v-if="$v.lastName.$dirty && !$v.lastName.minLength">At least two characters are required</p>

        <input type="text" class="form__input field" name="company" v-model="companyName" placeholder="Company name" />

        <input type="email" class="form__input field" name="email" v-model="email" placeholder="E-mail" @input="$v.email.$touch()" :class="{'errors': $v.email.$error}" />
        <p v-if="$v.email.$dirty && !$v.email.required">This field is required</p>
        <p v-if="$v.email.$dirty && !$v.email.email">Email address is incorrect</p>

        <textarea class="form__textarea field" name="message" v-model="message" placeholder="Message" style="font-family: 'Hind Siliguri'"  @input="$v.message.$touch()" :class="{'errors': $v.message.$error}"></textarea>
        <p v-if="$v.message.$dirty && !$v.message.required">This field is required</p>
        <p v-if="$v.message.$dirty && !$v.message.minLength">At least 20 characters are required</p>
        <p v-if="$v.message.$dirty && !$v.message.maxLength">The message requires less than 500 characters</p>

        <div class="form__terms">
            <input type="checkbox" class="form__input form__input--terms" v-model="$v.terms.$model" @change="$v.terms.$touch()" />
            <label class="form__terms--label special" :class="{ 'errors__text' : $v.terms.$dirty && $v.terms.$invalid}">I accept the terms and conditions
            </label> 
        </div>
        
        <button type="submit" class="form__btn field"  @click="checkForm">Send</button>
        <!-- <pre> {{ $v }}
        </pre> -->
    </form>
   
</template>
// 
<script>

import { validationMixin } from 'vuelidate';
import { required, minLength, maxLength, email, alpha } from 'vuelidate/lib/validators';

export default {
    name: "MyForm",
    mixins: [validationMixin],
    data() {
        return {
            firstName: "",
            lastName: "",
            companyName: "",
            email: "",
            message: "",
            terms: false,
            submitStatus: null
        }
    },
    validations: {
        firstName: {
            required,
            minLength: minLength(2)
        },
        lastName: {
            required,
            minLength: minLength(2)
        },
   
        email: {
            required,
            email
        },
        message: {
            required,
            minLength: minLength(20),
            maxLength: maxLength(500)
        },
        terms: {
            required,
            checked() {
                return this.terms === true ? true : false; 
            }
        }

    },
    methods: {
        
        checkForm() {
            this.$v.$touch()
            if(this.$v.$invalid) {
                
                alert("Please fill the form correctly.")
            } else {
                alert("Sending");
                setTimeout(() => {
                    alert("Thanks for your message!");
                }, 500)
            }

            
        }
    }
}
</script>

<style lang="scss" scoped>

@import "../styles/variables.scss";
@import "../styles/mixins.scss";

.field {
    font-size: 1.3rem;
    margin: 2rem 0;
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
        
        &--terms {
            margin-right: 1.5rem;
        }
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

    &__terms {
        display: flex;
        flex-direction: row;
        margin: 1rem 0 2rem;

        &--label {
            font-size: 1.5rem;
        }
    }

  
}

.special {
    font-weight: bold;
    color: $link-color;
}

.errors {
    border: 3px solid red;

    &__text {
        font-weight: bold;
        color: red;
    }
}


@media all and (max-width: 768px) {
    .form__input, .form__textarea {
        width: 70%;
    }

    .form__terms--label, .special {
        font-size: 1.2rem;
    }
}


</style>