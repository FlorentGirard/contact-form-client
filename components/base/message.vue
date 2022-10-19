<template>
  <div class="field">
    <label v-if="label" class="field__label"> {{ props.label }}</label>
    <textarea
      v-bind="$attrs"
      :id="props.label"
      class="field__input"
      :placeholder="props.placeholder"
    />
  </div>
</template>

<script lang="ts" setup>
const props = defineProps({
  label: {
    type: String,
    required: true,
  },
  placeholder: {
    type: String,
    default: '',
  },
  modelValue: {
    type: [String, Number],
    default: '',
  },
})
</script>

<style scoped lang="scss">
.field {
  margin: $gutter;

  &:last-child {
    margin-top: $gutter * 4.3;
  }
}
.field__input {
  width: 100%;
  border: 1px solid #ced0c2;
}
</style>
