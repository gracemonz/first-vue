<template>
  <div id="app">
    <!-- <sample contents> </sample> -->
    <MainHeader></MainHeader>
    <MainContent></MainContent>
    <MainFooter></MainFooter>
  </div>
</template>

<script>
import MainHeader from './components/header.vue'
import MainContent from './components/content.vue'
import MainFooter from './components/footer.vue'


export default {
  name: 'app',
  components: {
    // sample,
    MainHeader,
    MainContent,
    MainFooter,
  }
}
</script>

<!-- <style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale; 
  text-align: center;
  color: #2c3e50; 
  margin-top: 60px;
}
</style> -->
