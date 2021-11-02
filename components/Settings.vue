<template>
  <section class="settings">
    <div class="settings-container">
      <label>perspective: {{ transform.perspective }}px;</label>
      <input v-model="transform.perspective" type="range" min="0" max="999" @change="changeSettings">

      <label>rotateX: {{ transform.rotateX }}deg; </label>
      <input v-model="transform.rotateX" type="range" min="-180" max="180">

      <label>rotateY: {{ transform.rotateY }}deg; </label>
      <input v-model="transform.rotateY" type="range" min="-180" max="180">

      <label>rotateZ: {{ transform.rotateZ }}deg; </label>
      <input v-model="transform.rotateZ" type="range" min="-180" max="180">

      <button type="button">
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
    transform () {
      return this.transformValues
    }
  },
  methods: {
    changeSettings () {
      this.$emit('onChange', this.transform)
    }
  }
}
</script>

<style>

</style>
