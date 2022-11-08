<template>
  <div class="field">
    <label v-if="label" class="field__label"> {{ props.label }}</label>
    <textarea
      v-bind="$attrs"
      :id="props.label"
      class="field__input"
      :placeholder="props.placeholder"
      rows="5"
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
  margin: $gutter 0;

  &:last-child {
    margin-top: $gutter * 4.3;
  }
}

.field__label {
  font-size: $fontSize * 1.8;
  margin-bottom: $gutter * 0.8;
  display: block;
}
.field__input {
  width: 100%;
  border: 1px solid #ced0c2;

  &:focus {
    border-color: #36382e;
    box-shadow: 0 0 3px #36382e;
    -moz-box-shadow: 0 0 3px #36382e;
    -webkit-box-shadow: 0 0 3px #36382e;
    outline: none;
  }
}
</style>
