<template>
  <h1>CSS Playground</h1>
  <main>
    <Settings 
      @reset="reset" 
      v-model:perspective.number="transform.perspective" 
      v-model:rotate.number="transform.rotate" 
      v-model:rotateX.number="transform.rotateX" 
      v-model:rotateY.number="transform.rotateY" 
      v-model:rotateZ.number="transform.rotateZ" 
      v-model:skewX.number="transform.skewX" 
      v-model:skewY.number="transform.skewY" 
    />
    <Box :transform-values="transform" />
  </main>
</template>

<script>
import Settings from "./components/Settings.vue"
import Box from "./components/Box.vue"

export default {
  name: 'App',
  components: { Settings, Box },
  data() {
    return {
      transform: {
        perspective: 100,
        rotate: 0,
        rotateX: 0,
        rotateY: 0,
        rotateZ: 0,
        skewX: 0,
        skewY: 0
      }
    }
  },
  methods: {
    reset(newTransform) {
      this.transform = newTransform
    }
  }
}
</script>

<style>
html {
  box-sizing: border-box;
  width: 100%;
  height: 100%;
}

*,
*:before,
*:after {
  box-sizing: inherit;
  padding: 0;
  margin: 0;
}

body {
  font-family: Helvetica;
  background: #392759;
  height: 100%;
  margin: 0;
  display: flex; 
  align-items: center; 
  justify-content: center 
}

h1 {
  color: #8d81f3;
  text-align: center;
  font-size: 40px;
  margin-bottom: 80px;
}

main {
  display: flex;
  justify-content: space-around;
  align-items: center;
  max-width: 900px;
  margin: 0 auto;
  font-family: monospace, sans-serif;
  font-size: 20px;
}
</style>