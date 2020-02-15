<template>
 <div class="navbar">
<nav class="nav-wrapper blue">
  <div class="container">
     <a href="" class="brand-logo left">Authapp</a>
    <div class="nav-content right">
      <ul>
        <li><router-link  to="/" >Home</router-link>
        <li><router-link to="/login">Login</router-link></li>
        <li><router-link to="/register">Register</router-link></li>
        <li><router-link to="/about">about</router-link></li>
      </ul>
    </div>
  </div>
</nav>
    </div>
</template>

<script>
export default {
   name: 'Navbar'
}
</script>

<style>

</style>