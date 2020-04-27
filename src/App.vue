<template>
  <div id="app">
    <navigation />
    <router-view />
  </div>
</template>

<script>
import Navigation from './components/elements/Navigation';
export default {
  components: {
    Navigation
  }
};
</script>
