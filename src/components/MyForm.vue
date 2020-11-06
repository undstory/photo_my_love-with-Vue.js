<template>
    <form action="#" class="form" @submit.prevent>
       
        <input type="text" class="form__input field" name="firstName" v-model="firstName" placeholder="First name" @input="$v.firstName.$touch()" :class="{'errors': $v.firstName.$error}" />
        <p v-if="$v.firstName.$dirty && !$v.firstName.required">This field is required</p>
        <p v-if="$v.firstName.$dirty && !$v.firstName.minLength">At least two characters are required</p>
     
       
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
            <input type="checkbox" class="form__input form__input--terms" v-model="terms" @input="$v.terms.$touch()" :class="{'errors': $v.terms.$error}"/>
            <label class="form__terms--label special">I accept the terms and conditions
            </label> 
            <p v-if="$v.terms.$dirty && !$v.terms.required">This checkbox must be selected</p>
        </div>
        
        <button type="submit" class="form__btn field"  @click="checkForm">Send</button>
        <pre> {{ $v }}
        </pre>
    </form>
</template>
// 
<script>

import { validationMixin } from 'vuelidate';
import { required, minLength, maxLength, email } from 'vuelidate/lib/validators';

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
            terms: false
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
            maxLength: maxLength(25)
        },
        terms: {
            required
        }

    },
    methods: {
        
        checkForm() {
            this.$v.$touch()
            if(!this.$v.$anyError) {
                alert('Form is valid and ready to be submitted!');
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
}



</style>