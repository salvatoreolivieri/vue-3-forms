<!-- eslint-disable prettier/prettier -->
<template>
  <input
  type="checkbox"
    :checked="modelValue"
    @change="$emit('update:modelValue', $event.target.checked)"
    class="field"
  />
  <label>{{label}}</label>

</template>

<!-- eslint-disable prettier/prettier -->
<script>
export default {

  props:{

    label: {
      type: String,
      default: ""
    },

    modelValue: {
      type: Boolean,
      default: false
    }

  }
}
</script>

<!-- eslint-disable prettier/prettier -->
<style>

</style>