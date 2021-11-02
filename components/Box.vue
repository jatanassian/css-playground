<template>
  <section>
    <div class="box" :style="style" />
  </section>
</template>

<script>
export default {
  name: 'Box',
  props: {
    transformValues: Object
  },
  computed: {
    style () {
      return {
        transform: `
          perspective(${this.transformValues.perspective}px)
          rotateX(${this.transformValues.rotateX}deg)
          rotateY(${this.transformValues.rotateY}deg)
          rotateZ(${this.transformValues.rotateZ}deg)
        `
      }
    }
  }
}
</script>

<style>
.box {
  width: 150px;
  height: 150px;
  background: #8d81f3;
}
</style>
