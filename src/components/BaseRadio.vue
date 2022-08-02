<!-- eslint-disable prettier/prettier -->
<template>
  <input
      type="radio"
      :checked="value === modelValue"
      :value="value"

      @change="$emit('update:modelValue', value)"
      v-bind="$attrs"
    />
  <label>{{ label }}</label>
</template>

<!-- eslint-disable prettier/prettier -->
<script>
export default {

  props: {
    label:{
      type: String,
      default: ""
    },
    modelValue:{
      type: [String, Number],
      default:""
    },
    value:{
      type: [String, Number],
      required: true
    },
  }
}
</script>

<!-- eslint-disable prettier/prettier -->
<style>

</style>