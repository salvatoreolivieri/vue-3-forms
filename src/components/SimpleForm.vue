<!-- eslint-disable prettier/prettier -->
<template>
  <div>
    <h1>Create an event</h1>
    <form @submit.prevent="sendForm">
      <BaseSelect 
        label="Select a Category"
        v-model="event.category"
        :categories="categories"
        />

      <h3>Name & describe your event</h3>

      <BaseInput 
        v-model="event.title"
        label="Title"
        type="text"/>

      <BaseInput 
        v-model="event.description"
        label="Description"
        type="text"/>


      <h3>Where is your event?</h3>

      <BaseInput
        v-model="event.location"
        label="location"
        type="text"
      />


      <h3>Are pets allowed?</h3>
      <div>
        <BaseRadio 
          v-model="event.pets"
          :value="1"
          label="yes"
          name="pets"
        />
      </div>

      <div>
        <BaseRadio 
          v-model="event.pets"
          :value="0"
          label="no"
          name="pets"
        />
      </div>


      <h3>Extras</h3>

      <div>
        <BaseCheckbox
        v-model="event.extras.catering"
        label="catering"
        />
      </div>

      <div>
        <BaseCheckbox
        v-model="event.extras.music"
        label="music"
        />
      </div>

      <button class="button -fill-gradient" type="submit">Submit</button>
    </form>
  </div>
</template>

<!-- eslint-disable prettier/prettier -->
<script>

import axios from "axios";

export default {
    name: "SimpleForm",
    data() {
        return {
            categories: [
                "sustainability",
                "nature",
                "animal welfare",
                "housing",
                "education",
                "food",
                "community",
            ],
            event: {
                category: "",
                title: "",
                description: "",
                location: "",
                pets: 1,
                extras: {
                    catering: false,
                    music: false,
                },
            },
        };
    },

    methods: {
      sendForm(){
        axios.post('https://my-json-server.typicode.com/salvatoreolivieri/vue-3-forms/events', this.event) 
          .then( function (output) {
            console.log('this is the output:', output);
          })

          .catch( function (error) {
            console.log('this is the erro:', error);
          })
      }

    }
};
</script>
