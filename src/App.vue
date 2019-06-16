<template>
  <div id="app">
    <MangaResult
     :koma1=koma1
     :koma2=koma2
     :koma3=koma3
     />
    <Manga01
      key="koma1"
      v-if="step === 1"
      @next="handleNext1"
    />
    <Manga02
      key="koma2"
      v-if="step === 2"
      @next="handleNext2"
    />
    <Manga03
      key="koma3"
      v-if="step === 3"
      @next="handleNext3"
    />

  </div>
</template>

<script>
import Manga01 from './components/Manga01'
import Manga02 from './components/Manga02'
import Manga03 from './components/Manga03'
import MangaResult from './components/MangaResult'
export default {
  name: 'app',
  data() {
    return {
      step: 1,
      koma1: null,
      koma2: null,
      koma3: null,
    }
  },
  components: {
    Manga01,
    Manga02,
    Manga03,
    MangaResult
  },
  methods: {
    handleNext1(data) {
      this.koma1 = data.koma1
      this.step ++
   },
    handleNext2(data) {
      this.koma2 = data.koma2
      this.step ++
    },
    handleNext3(data) {
      this.koma3 = data.koma3
      this.step ++
    },
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

#app {
  font-family: sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  max-width: 640px;
  font-size: 12px;
  padding: 0 50px;
}
</style>