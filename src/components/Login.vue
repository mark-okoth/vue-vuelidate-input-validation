<template>
  <div class="login">
    <div class="container">
      <div class="container">
        <h3>Login</h3>
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
            <input type="submit" class="btn-small"/>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "Login"
};
</script>

<style>
</style>