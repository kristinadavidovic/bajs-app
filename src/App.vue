<template>
  <div id="app">
    <navigation navType="main" />
    <router-view />
    <navigation navType="footer" />
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
