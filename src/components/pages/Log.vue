<template>
  <div class="log">
    <h1>Log</h1>
    <AddLog />
  </div>
</template>

<script>
import AddLog from '../elements/AddLog';

export default {
  name: 'Log',
  components: {
    AddLog
  },
  computed: {
    dateTime: () => {
      return new Date().toISOString();
    }
  }
};
</script>
