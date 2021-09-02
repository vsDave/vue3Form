<template>
  <label class="m-2 text-xl">{{ label }}</label>

  <input
    v-bind="$attrs"
    class="p-2 m-3 bg-red-100 border border-black"
    :placeholder="label"
    :value="modelValue"
    @input="
      $emit(
        'update:modelValue',
        $event.target.value //$event.target.value is payload
      )
    "
  />
</template>
<script>
export default {
  props: {
    label: {
      type: String,
      default: '',
    },
    modelValue: {
      type: [String, Number],
      default: '',
    },
  },
}
</script>
