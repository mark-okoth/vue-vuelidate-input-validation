<template>
  <div class="register">
    <div class="card z-depth-0">
      <div class="container">
        <div class="container">
          <h3>Register</h3>
          <form action method>
            <div class="input-field">
              <input type="text" id="name" required v-model="name" />
              <label for="name">Name</label>
            </div>
            <div class="input-field" >
              <input type="email" id="email" :class="{invalid: $v.email.$error}" @blur="$v.email.$touch()" v-model="email" />
              <label for="email">Email</label>
              <p class="red-text" v-if="!$v.email.email">Please provide a valid Email</p>
              <p class="red-text" v-if="!$v.email.required">This field must not be empty</p>

            </div>

            <div class="input-field">
              <input type="text" id="user" required v-model="username" />
              <label for="user">Username</label>
            </div>

            <div class="input-field">
              <input type="number" required id="age" :class="{invalid: $v.age.$error}"  @blur="$v.age.$touch()" v-model.number="age" />
              <label for="age">Age</label>
              <p class="red-text" v-if="!$v.age.minVal"> Your age has to be at least {{ $v.age.$params.minVal.min}} years old </p>
            </div>

            <div class="input-field">
              <input type="password" id="password" required v-model="password" />
              <label for="password">Password</label>
            </div>
            <div class="input-field">
              <input type="password" id="password-confirm" v-model="confirmPassword" />
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
import { required, email, numeric, minValue } from "vuelidate/lib/validators";
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
    email: {
      required,
      email
    },
    age:{
      required,
      numeric,
      minVal: minValue(18)
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