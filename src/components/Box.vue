<template>
  <section>
    <div class="box-container">
      <div class="box" :style="style" />
    </div>
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
          rotate(${this.transformValues.rotate}deg)
          rotateX(${this.transformValues.rotateX}deg)
          rotateY(${this.transformValues.rotateY}deg)
          rotateZ(${this.transformValues.rotateZ}deg)
          skewX(${this.transformValues.skewX}deg)
          skewY(${this.transformValues.skewY}deg)
        `
      }
    }
  }
}
</script>

<style>
.box-container {
  padding: 100px;
  margin-left: 10px;
  border: 1px solid #8d81f3;
  overflow: hidden;
}

.box {
  width: 150px;
  height: 150px;
  background: #8d81f3;
}
</style>
