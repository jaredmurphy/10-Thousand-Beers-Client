<template>
  <div id="app">
    <img src="https://avatars0.githubusercontent.com/u/18290877?v=3&s=460">
    <Beer></Beer>
  </div>
</template>

<script>
import Beer from './components/Beer'

export default {
  name: 'app',
  components: {
    Beer
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

img {
  max-height: 300px;
}
</style>
