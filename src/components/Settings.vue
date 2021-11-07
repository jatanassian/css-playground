<template>
  <section class="settings">
    <div class="settings-container">
      <label>perspective: {{ transform.perspective }}px;</label>
      <input v-model="transform.perspective" type="range" min="0" max="999" @change="changeSettings">

      <label>rotateX: {{ rotateX }}deg; </label>
      <input v-model="rotateX" type="range" min="-180" max="180">

      <label>rotateY: {{ transform.rotateY }}deg; </label>
      <input v-model="transform.rotateY" type="range" min="-180" max="180" @input="changeSettings">

      <label>rotateZ: {{ transform.rotateZ }}deg; </label>
      <input v-model="transform.rotateZ" type="range" min="-180" max="180" @change="changeSettings">

      <label>skewX: {{ transform.skewX }}deg; </label>
      <input v-model="transform.skewX" type="range" min="-180" max="180" @change="changeSettings">

      <label>skewY: {{ transform.skewY }}deg; </label>
      <input v-model="transform.skewY" type="range" min="-180" max="180" @change="changeSettings">

      <button type="button" @click="reset">
        Reset
      </button>
      <button type="button">
        Copy
      </button>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Settings',
  props: {
    transformValues: Object
  },
  computed: {
    transform() {
      return { ...this.transformValues }
    },
    rotateX() {
        return this.transformValues.rotateX
    }
  },
  methods: {
    changeSettings () {
      console.log(123)
      this.$emit('onChange', this.transform)
    },
    reset () {
      console.log('hello')
      this.$emit('onChange', {
        perspective: 100,
        rotateX: 0,
        rotateY: 0,
        rotateZ: 0,
        skewX: 0,
        skewY: 0
      })
    }
  }
}
</script>

<style>

</style>
