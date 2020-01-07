<template>
  <div id="etin">
    <Header></Header>
    <HomePage msg="from parent" />
  </div>
</template>

<script>

import HomePage from './components/HomePage.vue'
import Header from './components/Header.vue'

export default {
  name: 'etin',
  components: {
    HomePage, 
    Header
  }
}
</script>

<style lang="scss">
  * { margin: 0; padding: 0; box-sizing: border-box;  }
  #etin {
    height: 100vh; 
    width: 100vw;
    background: #EEE; 
  }
      
</style>