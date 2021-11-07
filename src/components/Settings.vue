<template>
  <section class="settings">
    <div class="settings-container">
      <label>perspective: {{ transform.perspective }}px;</label>
      <input v-model="transform.perspective" type="range" min="0" max="999">

      <label>rotateX: {{ rotateX }}deg; </label>
      <input v-model="rotateX" type="range" min="-180" max="180">

      <label>rotateY: {{ rotateY }}deg; </label>
      <input :value="rotateY" type="range" min="-180" max="180" @input="updateValue('rotateY', $event.target.value)">

      <label>rotateZ: {{ transform.rotateZ }}deg; </label>
      <input v-model="transform.rotateZ" type="range" min="-180" max="180">

      <label>skewX: {{ transform.skewX }}deg; </label>
      <input v-model="transform.skewX" type="range" min="-180" max="180">

      <label>skewY: {{ transform.skewY }}deg; </label>
      <input v-model="transform.skewY" type="range" min="-180" max="180">

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
    transformValues: Object,
    rotateY: Number
  },
  emits: ["onChange", "update:rotateY"],
  computed: {
    transform() {
      return { ...this.transformValues }
    },
    rotateX: {
      get() {
        return this.transformValues.rotateX
      },
      set(newValue) {
        this.changeSettings("rotateX", newValue)
      }
    }
  },
  methods: {
    updateValue(property, value) {
      this.$emit(`update:${property}`, value)
    },
    reset() {
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
