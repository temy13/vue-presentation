<template lang="pug">
.root
  .height100(v-if="editMode")
    v-container.height100.grey.lighten-5
      v-row#input.height100(no-gutters='')
        v-col.height100(:key='0' :cols="3")
          v-card.height100.pa-2(tile='' outlined='')
            v-textarea.height100(rows="30" v-model="markdown")
        v-col#review.height100(:key='1' :cols="9")
          v-card.height100.pa-2(tile='' outlined='')
            mark-display(:markdown='markdown' :isFull="false" supportPreview='' keyboardCtrl='' autoFontSize='' )
  .height100(v-if="!editMode")
    mark-display(:markdown='markdown' :isFull="true" supportPreview='' keyboardCtrl='' autoFontSize='' )
</template>
<script>
import MarkDisplay from 'vue-mark-display'
import marked from 'marked'

// const markdown = `
// <!-- color: red; -->
// <!-- style: font-weight: bold; -->
//
// # This is First Slide
// Self intro here.
//
// ----
//
// <!-- stageBackground: silver -->
//
// ## The Second Slide
// - list item 1
// - list item 2
// - list item 3
//
// ----
//
// # The END
// Thanks.
// `
const markdown = `

<!-- color: red; -->

## 前提

既存システムの改修は無理

環境設定で終わる

----

\`\`\`horizontalAxis
- アカデミック
- 蒸留
- AI/ML(text clf)
- 開発(ML APIの組み込み)
- インタビューからの企画
- ビジネス
\`\`\`

`

export default {
  components: { MarkDisplay },
  props: {
    editMode: {
      type: Boolean,
      default: true
    }
  },
  data () {
    return {
      markdown: markdown
    }
  },
  methods: {
    setTitle ({ title }) {
      document.title = title
    }
  },
  computed: {
    markdownText: function () {
      return marked(this.markdown)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only  scoped lang="scss"-->
<style>
body {
  margin: 0;
}
.height100 {
  height: 100%;
  position: relative;
}
#review{
  position: relative;
}
#review .mark-display{
  height: 100%;
  width: 100%;
}
#review .slides{
  height: 100%;
  width: 100%;
  position: relative;
}
#review .slide{
  height: 100%;
  width: 100%;
}
#review .slide-content{
  height: 100%;
}
.horizontalAxis{
  width: 100%;
  position: relative;
}
.horizontalAxis li{
  list-style-type: none;
  float: left;
  width: 100px;
  text-align: center;
  font-size:20px;
}
.horizontalAxis li:first-child{
  position: absolute;
  left: 0;
  bottom: -20px;
}
.horizontalAxis li:last-child{
  position: absolute;
  right: 0;
  bottom: -20px;
}
</style>
