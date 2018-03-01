<template>
  <div class="stuff">
      <form id="application-input" v-on:submit.prevent method='POST'>
        <label>Apply Here: </label>
        <textarea id="application-text" rows="8" cols="100" v-model='application'></textarea>
        <input id="submit" type="submit" value="Submit" @click.prevent.reset="submitApp"/>
      </form>
      <p id="message"> {{message}}</p>
      <ThePreview v-bind:application="application"></ThePreview>
  </div>
</template>
<script>
    import ThePreview from "./ThePreview"

export default {
  name: "InputForm",
  components: {
    Preview
  },
  data() {
    return {
      application: '',
      message: ''
      }
    },
    methods: {
      submitApp(){
      this.message = 'Your application was submitted!'
    }
  }
}</script>
<style scoped>
</style>