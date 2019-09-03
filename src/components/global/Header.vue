<template lang="pug">
div
  v-app-bar(v-if="editMode" color='deep-purple accent-4')
    v-app-bar-nav-icon
    v-toolbar-title {{title}}
    //-.flex-grow-1
    //-v-btn(icon='')
      v-icon mdi-heart
    //-v-btn(icon='')
      v-icon mdi-magnify
    //-v-menu(left='' bottom='')
      template(v-slot:activator='{ on }')
        v-btn(icon='' v-on='on')
          v-icon mdi-dots-vertical
      v-list
        v-list-item(v-for='n in 5' :key='n' @click='() => {}')
          v-list-item-title Option {{ n }}
</template>
<script>
export default {
  name: 'Header',
  props: {
    title: {
      type: String,
      default: 'Presen'
    },
    editMode: {
      type: Boolean,
      default: true
    }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.slide-content{
  overflow-y: scroll;
}
</style>
