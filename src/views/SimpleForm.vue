<template>
  <div>
    <h1>Create an event</h1>
    <form @submit.prevent="onSubmit">

      <BaseSelect label="Select a category" :options="categories" v-model="event.category"/>

      <h3>Name & describe your event</h3>
      <BaseInput label="Title" type="text" v-model="event.title"/>
      <BaseInput label="Description" type="text" v-model="event.description"/>

      <h3>Where is your event?</h3>
      <BaseInput label="Location" type="text" v-model="event.location"/>

      <h3>Are pets allowed?</h3>
      <BaseRadioGroup vertical name="pets" :options="petOptions" v-model="event.pets"/>

      <h3>Extras</h3>
      <BaseCheckbox label="Catering" v-model="event.extras.catering"/>
      <BaseCheckbox label="Live music" v-model="event.extras.music"/>

      <button class="button -fill-gradient" type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data () {
    return {
      categories: [
        'sustainability',
        'nature',
        'animal welfare',
        'housing',
        'education',
        'food',
        'community'
      ],
      petOptions: [
        { label: 'Yes', value: '1' },
        { label: 'No', value: '0' }
      ],
      event: {
        category: '',
        title: '',
        description: '',
        location: '',
        pets: 1,
        extras: {
          catering: false,
          music: false
        }
      }
    }
  },
  methods: {
    onSubmit () {
      axios.post('http://localhost:3000/event', this.event)
        .then((response) => console.log(response))
        .catch((err) => console.log(err))
    }
  }
}
</script>
