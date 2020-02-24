<template>
  <div class="register">
    <div class="card z-depth-0">
      <div class="container">
        <div class="container">
          <h3>Register</h3>
          <form @submit.prevent="formvalidation">
            <div class="input-field">
              <input type="text" id="name" :class="{invalid: $v.name.error}" @input="$v.name.$touch()" required v-model="name" />
              <label for="name">Name</label>
              <p  v-if="!$v.name.required" class="red-text">Please enter your name </p>
            </div>
            <div class="input-field" >
              <input type="email" id="email" :class="{invalid: $v.email.$error}" @blur="$v.email.$touch()" v-model="email" />
              <label for="email">Email</label>
              <p class="red-text" v-if="!$v.email.email">Please provide a valid Email</p>
              <p class="red-text" v-if="!$v.email.required">This field must not be empty</p>

            </div>

            <div class="input-field">
              <input type="text" id="user" :class="{invalid: $v.username.$error}" @blur="$v.username.$touch()" required v-model="username" />
              <label for="user">Username</label>
              <p v-if="!$v.username.required" class="red-text">Please enter a user name</p>
            </div>

            <div class="input-field">
              <input type="number" required id="age" :class="{invalid: $v.age.$error}"  @blur="$v.age.$touch()" v-model.number="age" />
              <label for="age">Age</label>
              <p class="red-text" v-if="!$v.age.minVal"> Your age has to be at least {{ $v.age.$params.minVal.min}} years old </p>
            </div>

            <div class="input-field">
              <input type="password" id="password" :class="{invalid: $v.password.$error }" @blur="$v.password.$touch()" required v-model="password" />
              <label for="password">Password</label>
            </div>
            <div class="input-field">
              <input type="password" id="password-confirm" :class="{invalid: $v.confirmPassword.$error}" @blur="$v.confirmPassword.$touch()" v-model="confirmPassword" />
              <label for="password-confirm">Confirm Password</label>
            </div>
            <button class="waves-effect btn-small blue" type="submit">Submit</button>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { required, email, numeric, minValue, minLength, sameAs} from "vuelidate/lib/validators";
export default {
  name: "Register",
  data() {
    return {
      name: "",
      email: "",
      age: null,
      username: "",
      password: "",
      confirmPassword: ""
    };
  },
  validations: {
    name:{
     required
    },
    email: {
      required,
      email
    },

    username:{
     required
    },
    age:{
      required,
      numeric,
      minVal: minValue(18)
    },
    password:{
      required,
      minLen:minLength(6)
    },
    confirmPassword:{
     sameAs:sameAs('password')
    }
  }
};
</script>


<style>
.input-field.invalid label {
  color: red;
}

.input-field.invalid {
  border: 1px solid red;
  border-top: red;
  background-color: #ffc9aa;
}
</style>