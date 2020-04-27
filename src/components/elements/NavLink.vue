<template>
  <router-link :to="url">
    <slot></slot>
  </router-link>
</template>

<script>
export default {
  name: 'nav-link',
  props: {
    url: {
      required: true,
      type: String
    }
  }
};
</script>
