<template>
  <a v-if="to !== ''" :href="to" target="_blank" rel="noopener">
    <slot />
  </a>
</template>
<script>
export default {
  props: {
    to: {
      type: String,
      required: true,
      default: ""
    }
  }
};
</script>
