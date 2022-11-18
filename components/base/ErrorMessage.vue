<template>
  <p :id="props.id" aria-live="assertive" class="errorMessage">
    <slot />
  </p>
</template>

<script lang="ts" setup>
const props = defineProps({
  id: {
    type: [String, Number],
    required: true,
  },
})
</script>

<style scoped lang="scss">
.errorMessage {
  color: $colorError;
  padding-top: $gutter * 0.5;
}
</style>
