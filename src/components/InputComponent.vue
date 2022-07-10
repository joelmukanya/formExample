<template>
  <fieldset>
    <legend>Form Details</legend>
    <form>
      <div v-for="p in person" :key="p.id">
        <input :type="p.type" v-model="p.value" :placeholder="p.placeholder"/>
        <p>{{p.value}}</p>
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
  }
}
</script>

<style>

</style>