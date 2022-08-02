<!-- eslint-disable prettier/prettier -->
<template>

  <label> {{ label }} </label>
  <input
        v-bind="$attrs"
        :placeholder="label"
        class="field"
        :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)"
      />


    <!--

        v-bind="$attrs" : Questo serve per passargli gli stili pooichè ci sono più elementi nel componente
 
        :placeholder="label" : Questo prende il placeholder in modo dinamico

        class="field" : Questa è semplicemente la classe

        :value="modelValue" : Questo è il v-model

        @input="$emit('update:modelValue', event.target.value)" : Con l'emit aggiorniamo il v-model

    -->

  
</template>

<!-- eslint-disable prettier/prettier -->
<script>
export default {
    props: {
      label:{
        type: String,
        default: "",
      },

      modelValue: {
        type: [String, Number],
        default: ""
      }

    },
}
</script>

<!-- eslint-disable prettier/prettier -->
<style>

</style>
