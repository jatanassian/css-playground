<template>
  <section class="settings">
    <div class="settings-container">
      <label>perspective: {{ perspective }}px;</label>
      <input :value="perspective" type="range" min="0" max="999" @input="updateValue('perspective', $event.target.value)">

      <label>rotate: {{ rotate }}deg; </label>
      <input :value="rotate" type="range" min="-180" max="180" @input="updateValue('rotate', $event.target.value)">

      <label>rotateX: {{ rotateX }}deg; </label>
      <input :value="rotateX" type="range" min="-180" max="180" @input="updateValue('rotateX', $event.target.value)">

      <label>rotateY: {{ rotateY }}deg; </label>
      <input :value="rotateY" type="range" min="-180" max="180" @input="updateValue('rotateY', $event.target.value)">

      <label>rotateZ: {{ rotateZ }}deg; </label>
      <input :value="rotateZ" type="range" min="-180" max="180" @input="updateValue('rotateZ', $event.target.value)">

      <label>skewX: {{ skewX }}deg; </label>
      <input :value="skewX" type="range" min="-180" max="180" @input="updateValue('skewX', $event.target.value)">

      <label>skewY: {{ skewY }}deg; </label>
      <input :value="skewY" type="range" min="-180" max="180" @input="updateValue('skewY', $event.target.value)">

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
    perspective: Number,
    rotate: Number,
    rotateX: Number,
    rotateY: Number,
    rotateZ: Number,
    skewX: Number,
    skewY: Number
  },
  emits: ["reset", "update:perspective", "update:rotate", "update:rotateX", "update:rotateY", "update:rotateZ", "update:skewX", "update:skewY",],
  methods: {
    updateValue(property, value) {
      this.$emit(`update:${property}`, value)
    },
    reset() {
      this.$emit('reset', {
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
