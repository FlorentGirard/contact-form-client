<template>
  <div class="field">
    <label v-if="props.label" class="field__label"> {{ props.label }}</label>
    <input
      v-bind="$attrs"
      :id="props.label"
      :value="props.modelValue"
      class="field__input"
      :class="{
        'field__input--error': props.error,
        'field__input--icon-rtl': props.error,
      }"
      :placeholder="props.placeholder"
      :aria-describedby="props.error ? `${props.label}-error` : null"
      :aria-invalid="props.error ? true : null"
      @input="$emit('update:modelValue', $event.target.value)"
    />
    <BaseErrorMessage v-if="props.error" :id="`${props.label}-error`">
      {{ props.error }}
    </BaseErrorMessage>
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
  error: {
    type: String,
    default: '',
  },
})
</script>

<style scoped lang="scss">
.field {
  margin: $gutter 0;
}
.field__label {
  font-size: $fontSize * 1.8;
  margin-bottom: $gutter * 0.8;
  display: block;
}
.field__input {
  width: 100%;
  border: 1px solid #ced0c2;
  height: 32px;
  border-radius: 4px;

  &:focus {
    border-color: #36382e;
    box-shadow: 0 0 3px #36382e;
    -moz-box-shadow: 0 0 3px #36382e;
    -webkit-box-shadow: 0 0 3px #36382e;
    outline: none;
  }

  &--error {
    border-color: $colorError;
  }

  &--icon-rtl {
    background-image: url('/picture/svg/warning.svg');
    background-position: 98%;
    background-repeat: no-repeat;
    background-size: 20px;
  }
}
</style>
