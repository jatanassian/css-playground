<template>
  <main>
    <h1>CSS Playground</h1>
    <Settings :transform-values="transform" />
    <Box :transform-values="transform" />
  </main>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      transform: {
        perspective: 100,
        rotateX: 0,
        rotateY: 0,
        rotateZ: 0
      }
    }
  },
  methods: {
    changeSettings (newTransform) {
      this.transform = newTransform
    }
  }
}
</script>
