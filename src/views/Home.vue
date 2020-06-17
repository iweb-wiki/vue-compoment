<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <ScrollNav msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import ScrollNav from '@/components/ScrollNav.vue';

export default {
  name: 'Home',
  components: {
    ScrollNav,
  },
};
</script>
