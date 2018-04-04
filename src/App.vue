
<template>
  <div id="app">
    <TheHeader/>
    <main>
      <TheJobDetails/>
      <TheForm :getText="getText"/>
      <button id="preview-toggle" @click="togglePreview = !togglePreview">Show Preview</button>
      <ThePreview :text="applicationText" :class="{hidden : togglePreview}"/>
    </main>
    <TheFooter/>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader"
import TheFooter from "./components/TheFooter"
import TheJobDetails from "./components/TheJobDetails"
import TheForm from "./components/TheForm"
import ThePreview from "./components/ThePreview"
export default {
  name: "app",
  components: {
    TheHeader,
    TheFooter,
    TheJobDetails,
    TheForm,
    ThePreview
  },
  data () {
    return {
      togglePreview: true,
      applicationText: ""
    }
  },
  methods: {
    getText(text) {
      this.applicationText = text;
    }
  }
}
</script>

<style>
	html {
	  margin: 0;
	  padding: 0;
	}
	main {
	  grid-row: 2/3;
	  width: 70%;
	  margin: 0 auto;
	  padding: 10px;
	}
	small {
	  color: black;
	  font-size: .5rem;
	  margin-left: 10px;
	}
	a {
	  color: #C261CC;
	  text-decoration: none;
	}
	.hidden {
	  display: none;
	}
</style>