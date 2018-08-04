<template>
  <div id="app">
    <h2>Default</h2>
    <p>no props, will generate random icons <a href="https://github.com/ethereum/blockies#readme">see defaults</a>
    <div v-for="i in 10" >
      <blockies v-for="j in 10"  />
    </div>

    <h2>With size props</h2>
    <div v-for="i in 10" >
      <blockies v-for="j in 10"  :opts="{
        // seed: 'randstring', // seed used to generate icon data, default: random
        // color: '#dfe', // to manually specify the icon color, default: random
        // bgcolor: '#aaa', // choose a different background color, default: random
        size: 15, // width/height of the icon in blocks, default: 8
        scale: 3, // width/height of each block in pixels, default: 4
        // spotcolor: '#000' // each pixel has a 13% chance of being of a third color,
        }" />
    </div>

    <h2>With same seed, same results</h2>

    <div v-for="i in 10" >
      <blockies v-for="j in 10"  :opts="{
        color: '#dfe',
        bgcolor: '#fff',
        spotcolor: '#000',
        seed: 'seedidrepeated', // seed used to generate icon data, default: random
        size: 15, // width/height of the icon in blocks, default: 8
        scale: 3, // width/height of each block in pixels, default: 4
        }" />
    </div>
  </div>
</template>

<script>
import blockies from './components/blockies.vue'

export default {
  name: 'app',
  components: {
    blockies
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
