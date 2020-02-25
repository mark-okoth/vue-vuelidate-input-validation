<template>
  <div class="login">
    <div class="container">
      <div class="container">
        <h3>Login</h3>
        <form @submit.prevent="sublition">
          <div class="input-field">
            <input type="email" id="name" :class="{invalid : $v.email.$error}" @blur="$v.email.$touch()" required v-model="email" />
            <label for="name">Email</label>
            <p class="red-text" v-if="!$v.email.email">please enter a valid email address</p>
             <p class="red-text" v-if="!$v.email.required">you connot leave this input blank</p>
          </div>
          <div class="input-field">
            <input type="password" id="password" :class="{invalid: $v.password.$error}" @blur="$v.password.$touch()" v-model="password" required />
            <label for="password">Password</label>
          </div>
          <div class="input-field">
            <input type="submit" class="btn-small" />
          </div>
        </form>
      </div>
    </div>
  </div>
</template>


<script>
import { required, minLength, email } from 'vuelidate/lib/validators'
export default {
  name: "Login", 
  data(){
    return{
     email: "",
     password: ""
    }
  },
  validations:{
    email:{
      required, 
      email
    },
    password:{
     minLen: minLength(6),
     required
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