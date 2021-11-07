<template>
  <main>
    <h1>CSS Playground</h1>
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

