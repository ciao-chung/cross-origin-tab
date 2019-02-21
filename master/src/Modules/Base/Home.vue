<template>
  <div page="home">
    <img src="~/assets/logo.png">
    <h1>Master</h1>
    <p class="home">Master</p>

    <button @click="openNewTab">開新分頁(Child)</button>
  </div>
</template>

<script lang="babel" type="text/babel">
import AcrossTabs from 'across-tabs'
export default {
  data() {
    return {
      parent: null,
    }
  },
  created() {
    // parent
    this.parent = new AcrossTabs.Parent({
      onHandshakeCallback: () => {
        console.warn('建立通訊完成')
      },
      onChildCommunication: (data) => {
        console.warn('child呼叫master', data)
      },
    })
  },
  methods: {
    openNewTab() {
      this.parent.openNewTab({url: 'http://localhost:8081', windowName: 'AcrossTab'})
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