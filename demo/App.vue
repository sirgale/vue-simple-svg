<template>
  <div id="app">
    <div class="container">
      <SvgButton
        :svg-src="'/demo/assets/' + filename"
      />
      <ChangeSrcButton
        class="margin-top-20"
        @click="changeSvgSrc"
      />
    </div>
  </div>
</template>

<script>
import SvgButton from './components/SvgButton'
import ChangeSrcButton from './components/ChangeSrcButton'
require('reset.css')
const svgFiles = ['ufo.svg', 'dinosaur.svg', 'robot.svg']
//const svgFiles = ['kron.svg', 'kron4.svg', 'CI.svg']  // предлагаю работать через эти файлы (чисто для Space, для проверки)
//const svgFiles = ['kron.svg', 'kron4.svg', 'CI.svg']  // все это можно удалить
//const svgFiles = ['kron.pas', 'kron4.pas', 'CI.pas']  // не только можно, но и нужно


export default {
  name: 'app',
  components: {
    SvgButton,
    ChangeSrcButton
  },
  data () {
    return {
      fileIndex: 0
    }
  },
  computed: {
    filename () {
      return svgFiles[this.fileIndex]
    }
  },
  methods: {
    changeSvgSrc () {
      this.fileIndex++
      if (this.fileIndex >= svgFiles.length) this.fileIndex = 0
    }
  }
}
</script>

<style>
html, body, #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;

  background-color: seagreen;
  height: 100%;
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
}

.margin-top-20 {
  margin-top: 20px;
}
</style>
