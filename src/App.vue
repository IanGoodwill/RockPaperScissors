<template>
  <div id="app">
  <RockPaperScissors/>
  </div>
</template>

<script>
import RockPaperScissors from './components/RockPaperScissors.vue'

export default {
  name: 'App',
  components: {
    RockPaperScissors
  }

  
}
</script>

<style>
#app {
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  margin-top: 60px;
	background-image: linear-gradient(45deg, rgb(53, 77, 116), rgb(84, 125, 157));
	z-index: -1;

 
}
</style>
