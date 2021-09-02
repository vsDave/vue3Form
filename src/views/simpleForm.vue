<template>
  <div class="m-5">
    <h1 class="m-3 text-3xl font-semibold">Create an event</h1>
    <form @submit.prevent="sendForm">
      <baseSelect
        class="m-3 border border-black"
        :options="categories"
        v-model="event.category"
        label="select a category"
      />
      <h3 class="m-3 text-xl font-semibold">Name & describe your event</h3>
      <BaseInput v-model="event.title" label="title" type="text" />
      <BaseInput v-model="event.description" label="Description" type="text" />

      <h3 class="m-3 text-xl font-semibold">Where is your event?</h3>

      <BaseInput v-model="event.location" label="Location" type="text" />

      <h3 class="m-3 text-xl font-semibold">Are pets allowed?</h3>
      <div class="m-3">
        <baseRadioGroup
          v-model="event.pets"
          name="pets"
          :options="petOptions"
        />
      </div>

      <!-- <div class="m-3">
        <baseRadio v-model="event.pets" :value="0" label="No" name="pets" />
      </div> -->

      <h3 class="m-3 text-xl font-semibold">Extras</h3>
      <div class="m-3">
        <baseCheckbox v-model="event.extras.catering" label="  Catering" />
      </div>

      <div class="m-3">
        <baseCheckbox v-model="event.extras.music" label="  Live music" />
      </div>

      <button class="p-2 m-3 text-white bg-black" type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios'
import BaseInput from '../components/baseInput.vue'
import baseSelect from '../components/baseSelect.vue'
import baseCheckbox from '../components/baseCheckbox.vue'
import baseRadioGroup from '../components/baseRadioGroup.vue'

export default {
  components: {
    BaseInput,
    baseSelect,
    baseCheckbox,
    baseRadioGroup,
  },
  data() {
    return {
      categories: [
        'sustainability',
        'nature',
        'animal welfare',
        'housing',
        'education',
        'food',
        'community',
      ],
      event: {
        category: '',
        title: '',
        description: '',
        location: '',
        pets: 1,
        extras: {
          catering: false,
          music: false,
        },
      },
      petOptions: [
        { label: 'yes', value: 1 },
        { label: 'no', value: 0 },
      ],
    }
  },
  methods: {
    sendForm() {
      axios
        .post(
          'https://my-json-server.typicode.com/Code-Pop/Vue-3-Forms/events',
          this.event
        )
        .then(function (response) {
          console.log(response, 'before')
          console.log(this.event, 'event')
          // this.event.push(response)
          // console.log(this.event, 'after')
        })
        .catch(function (error) {
          console.log(error, 'error')
        })
    },
  },
}
</script>
