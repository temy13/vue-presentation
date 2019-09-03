<template lang="pug">
  #app
    gheader(:title="title" :editMode="editMode")
    router-view(:editMode="editMode")

    .mode-switch
      v-btn.mx-2(v-if="editMode" fab='' dark='' small='' color='primary' v-on:click="editMode = false")
        v-icon(dark='') mdi-fullscreen
      v-btn.mx-2(v-if="!editMode" fab='' dark='' small='' color='primary' v-on:click="editMode = true")
        v-icon(dark='') mdi-fullscreen-exit
</template>

<script>

import Header from '@/components/global/Header'

export default {
  name: 'App',
  components: {
    gheader: Header
  },
  data () {
    return {
      title: 'Markdown Presentation',
      editMode: true
    }
  }
}
</script>

<style>
* :not(.v-icon) {
  font-family: "Hiragino Kaku Gothic Pro","メイリオ", sans-serif!important;
}
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
.mode-switch{
  position: absolute;
  bottom: 5%;
  right: 5%;
}
</style>
