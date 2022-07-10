<template>
  <fieldset>
    <legend>Form Details</legend>
    <form @submit.prevent="readyToSubmit">
      <div v-for="p in person" :key="p.id">
        <input :type="p.type" v-model="p.value" :placeholder="p.placeholder"/>
        <p>{{p.value}}</p>
      </div>
      <div>
        <span>Position: </span>
        <select v-model="jobTitle">
          <option value="lecturer">Lecturer</option>
          <option value="developer">Developer</option>
          <option value="Admin">Admin</option>          
        </select>
          <p style="margin: 5px 0;">Your Job title is <strong>{{jobTitle}}</strong></p>
      </div>
      <div>
        <h2>Select your favor fruit(s)</h2>
        <div class="inline-wrapper">
          <input type="checkbox" value="Mango" v-model="fruits">
          <span>Mango</span>
        </div>
        <div class="inline-wrapper">
          <input type="checkbox" value="Orange" v-model="fruits">
          <span>Orange</span>
        </div>
        <div class="inline-wrapper">
          <input type="checkbox" value="Banana" v-model="fruits">
          <span>Banana</span>
        </div>
        <div class="inline-wrapper">
          <input type="checkbox" value="Pineapple" v-model="fruits">
          <span>Pineapple</span>
        </div>
        <p v-for="(fruit, index) in fruits" :key="index">
          <span>{{fruit}}</span>
        </p>
      </div>
      <div>
        <p>
          {{ result }}
        </p>
      </div>
      <div>
        <button>Submit</button>
      </div>
    </form>
  </fieldset>
</template>

<script>
export default {
  data() {
    return {
      jobTitle: 'lecturer',
      fruits: [],
      result: '',
      person: [
        {
          id: 1,
          type: 'text',
          value: '',
          placeholder: 'Enter your name'
        },
        {
          id: 2,
          type: 'text',
          value: '',
          placeholder: 'Enter your surname'
        },
        {
          id: 3,
          type: 'email',
          value: '',
          placeholder: 'Enter your email'
        }
      ]
    }
  },
  methods: {
    readyToSubmit() {
      this.result = "Form was submitted";
    }
  }
}
</script>

<style>

</style>