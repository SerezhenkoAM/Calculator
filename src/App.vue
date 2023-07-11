<template>
  <div class="app">  
    <HomePage class="homepage"/>
  </div>
</template>

<script>
import HomePage from './components/HomePage.vue'

export default {
  name: 'App',
  components: {
    HomePage
  }
}
</script>

<style>

body {
  background-color: #e5e5e5;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}

.homepage {
  margin: 0 auto;
}

.app {
  height: 97vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
