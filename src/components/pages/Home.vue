<template>
  <div class="home">
    <h1>This is a home page.</h1>
    <navLink url="log-poop">Log</navLink>
  </div>
</template>

<script>
import NavLink from '../elements/NavLink';

export default {
  name: 'Home',
  components: {
    NavLink
  }
};
</script>
