<template>
  <div class="register">
    <div class="card z-depth-0">
      <div class="container">
        <div class="container">
          <h3>Register</h3>
          <form action method>
            <div class="input-field">
              <input type="text" id="name" required />
              <label for="name">Name</label>
            </div>
            <div class="input-field">
              <input type="email" id="email" required />
              <label for="email">Email</label>
            </div>

            <div class="input-field">
              <input type="text" id="user" required />
              <label for="user">Username</label>
            </div>

            <div class="input-field">
              <input type="date" required id="age" />
            </div>

            <div class="input-field">
              <input type="password" id="password" required />
              <label for="password">Password</label>
            </div>
            <div class="input-field">
              <input type="password" id="password-confirm" />
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
export default {
  name: "Register"
};
</script>


<style>
</style>