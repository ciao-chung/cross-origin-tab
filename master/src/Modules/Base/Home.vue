<template>
  <div page="home">
    <img src="~/assets/logo.png">
    <h1>Master</h1>
    <p class="home">Master</p>
  </div>
</template>

<script lang="babel" type="text/babel">
export default {
  async created() {
    console.warn('create')
    const result = await this.foo()
    console.warn(result)
  },
  methods: {
    async wait(ms) {
      return new Promise(resolve => {
        setTimeout(() => resolve() , ms)
      })
    },
    async foo() {
      await this.wait(2000)
      return { foo: 'bar' }
    },
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