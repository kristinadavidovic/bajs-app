<template>
  <a class="button" :class="`button--${type}`">
    <slot></slot>
  </a>
</template>

<script>
export default {
  name: 'Button',
  props: {
    type: {
      required: true,
      type: String,
    },
  },
}
</script>
