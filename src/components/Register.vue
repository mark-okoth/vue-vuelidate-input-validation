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
            <div class="input-field" :class="{invalid: $v.email.$error}">
              <input type="email" id="email" @blur="$v.email.$touch()" v-model="email" />
              <label for="email">Email</label>
              <p v-if="!$v.email.email"> please provide a valid Email</p>
              <p v-if="!$v.email.required">This field must not be empty</p>
            </div>

            <div class="input-field">
              <input type="text" id="user" required v-model="username" />
              <label for="user">Username</label>
            </div>

            <div class="input-field">
              <input type="number" required id="age" v-model.number="age" />
              <label for="age">Age</label>
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
import { required, email } from "vuelidate/lib/validators";
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
  background-color: #ffc9aa;
}
</style>