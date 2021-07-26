<template lang="pug">
  .portfolio-card
    template(v-if="$slots.default")
      slot
    template(v-else)
      .portfolio-card__img(
        :style="`background-image: url(${imgSrc})`"
      )
      .portfolio-card__brand(v-if="brand")
        .portfolio-card__brand-name
          | {{ brand }}
</template>

<script>
export default {
  props: {
    brand: {
      type: String,
      default: '',
    },
    imgSrc: {
      type: String,
      default: '',
    },
  },
}
</script>
<style lang="scss" scoped>
.portfolio-card {
  position: relative;
  display: flex;
  border-radius: 6px;
  overflow: hidden;
  cursor: pointer;
  background-color: map-get($colors, bg-white);

  &:hover .portfolio-card__img {
    transform: scale(1.2);
  }

  .portfolio-card__img {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-size: cover;
    transition: all 0.5s ease-in-out;
  }

  .portfolio-card__brand {
    position: relative;
    z-index: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    flex: 1;
    background: rgba(107, 107, 107, 0.7);
  }

  .portfolio-card__brand-name {
    color: #fff;
    font-weight: bold;
    font-size: 44px;
    line-height: 48px;
    text-align: center;
    text-transform: uppercase;
    word-wrap: break-word;
  }
}
</style>
