<template lang="pug">
  .section-badge(
    :class="{'bg-colorless': src, absolute}"
    :style="getStyle()"
  )
    .section-title(v-if="$slots.default")
      slot
</template>

<script>
export default {
  props: {
    src: {
      type: String,
      default: '',
    },
    absolute: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    getStyle() {
      if (this.src) return `background-image: url(${this.src})`
      return ''
    },
  },
}
</script>

<style lang="scss" scoped>
.section-badge {
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
  width: 180px;
  height: 230px;
  padding: 30px 20px;
  background-color: map-get($colors, primary-purple);
  background-size: cover;
  background-repeat: no-repeat;
  border-radius: 10px;
  color: #fff;
  overflow: hidden;

  &.bg-colorless {
    background-color: transparent;
  }

  &.absolute {
    position: absolute;
    top: 0;
    left: 0;
  }
}
</style>
