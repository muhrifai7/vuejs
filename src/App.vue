<template>
  <div id="app">
    <Navbar
      name="Test"
      :navLinks="[
        {
          name: 'Home',
          link: '/home',
          dropdown: false,
        },
        { name: 'Discover', link: '/discover', dropdown: false },
        {
          name: 'Register',
          link: '/register',
          dropdown: false,
        },
        { name: 'Search', link: '/search', dropdown: false },
      ]"
    />
  </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue';
// import Home from '@/components/Home.vue';
export default {
  name: 'App',
  components: {
    Navbar,
    // Home
  },
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body{
  overflow-x: hidden;
}
</style>