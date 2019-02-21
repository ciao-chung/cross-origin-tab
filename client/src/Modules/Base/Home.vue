<template>
  <div page="home">
    <img src="~/assets/logo.png">
    <h1>Client</h1>
    <p class="home">Client</p>

    <button @click="communication">通知Master</button>
  </div>
</template>

<script lang="babel" type="text/babel">
import AcrossTabs from 'across-tabs'
export default {
  data() {
    return {
      child: null,
    }
  },
  created() {
    // child
    this.child = new AcrossTabs.Child({

    })
  },
  methods: {
    communication() {
      this.child.sendMessageToParent({ action: 'someAction' })
    }
  },
}
</script>

<style lang="sass" type="text/sass">
#app
  font-family: 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  text-align: center
  color: #2c3e50
  margin-top: 60px
div[page="home"]
  transition: all 0.5s ease
  img
    width: 120px
  p
    color: gray
</style>