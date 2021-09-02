<template>
  <label v-if="label">
    <input
      type="checkbox"
      :checked="modelValue"
      @change="$emit('update:modelValue', $event.target.checked)"
    />{{ label }}</label
  >
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: '',
    },
    modelValue: {
      type: Boolean,
      default: false,
    },
  },
}
//checkbox inputs bind their state to a checked property and not directly to value.
//and @change instead of @input
</script>

<style></style>
