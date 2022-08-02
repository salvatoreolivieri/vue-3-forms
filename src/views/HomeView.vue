<template>
  <div class="home">
    <SimpleForm />
  </div>
</template>

<script>
// @ is an alias to /src
import SimpleForm from "../components/SimpleForm.vue";

export default {
  name: "HomeView",
  components: {
    SimpleForm,
  },
};
</script>
