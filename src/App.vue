<template lang="pug">
  #app
    //-header
    router-view
</template>

<script>

// import Header from '@/components/global/Header'

export default {
  name: 'App'
  // components: {
  //   header: Header
  // }
}
</script>

<style>
html, body{
  height:100%;
}
#app, .root{
  height: 100%;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
