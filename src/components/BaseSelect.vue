<!-- eslint-disable prettier/prettier -->
<template>
  <label>{{ label }}</label>
      <select
        :value="modelValue"

        v-bind="{
          ...$attrs,
          onChange: ($event) => {$emit ('update:modelValue' , $event.target.value)}
        }">

        <option
          v-for="option in categories"
          :value="option"
          :key="option"

          :selected="option === modelValue"

        >
        
          {{ option }}
        </option>
      </select>
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

    categories: {
      type: Array,
      required: true
    }
  }

}
</script>

<!-- eslint-disable prettier/prettier -->
<style>

</style>