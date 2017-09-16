<template>
  <div class="homeapp">
      <h1>This is Home component </h1>
      <transition mode="out-in">
        <component v-bind:is="currentView"></component>
      </transition>
       <button @click="changeView()">Click Me!</button>
  </div>
</template>

<script>
import Page from '../components/Page.vue'
import PageTwo from '../components/PageTwo.vue'

export default {
  name: 'home',
  data () {
    return {
      currentView: Page
    }
  },
  methods: {
    changeView () {
      console.log(this)
      console.log(this.currentView.name)
      if (this.currentView.name === 'page') {
        this.currentView = PageTwo
      } else if (this.currentView.name === 'pagetwo') {
        this.currentView = Page
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
