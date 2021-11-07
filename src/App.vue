<template>
  <main>
    <h1>CSS Playground</h1>
    <Settings :transform-values="transform" @on-change="changeSettings" v-model:rotateY.number="transform.rotateY" />
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
        rotateX: 0,
        rotateY: 0,
        rotateZ: 0,
        skewX: 0,
        skewY: 0
      }
    }
  },
  methods: {
    changeSettings(newTransform) {
      console.log("changing settings from App")
      this.transform = newTransform
    }
  }
}
</script>

