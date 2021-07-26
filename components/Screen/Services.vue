<template lang="pug">
  section.section.section--services
    .large-container
      .services__wrapper
        .services__content
          section-badge(absolute)
            | Услуги

          .services__swiper-wrapper
            .services__swiper-nav
              button#swiper-services-button-prev
                NavArrow
              button#swiper-services-button-next
                NavArrow

            swiper.services__swiper(
              :options="swiperOptions"
            )
              swiper-slide(v-for="id in 10")
                card-slider-service
</template>

<script>
import NavArrow from '~/assets/svg/nav-arrow.svg?inline'

export default {
  components: {
    NavArrow,
  },
  data() {
    return {
      swiperOptions: {
        speed: 600,
        slidesPerView: 4,
        spaceBetween: 15,
        autoresize: true,
        navigation: {
          nextEl: '#swiper-services-button-next',
          prevEl: '#swiper-services-button-prev',
        },
      },
    }
  },
}
</script>

<style lang="scss" scoped>
.section--services {
  position: relative;
  padding: 120px 0 20px;

  &::before {
    position: absolute;
    z-index: -1;
    display: block;
    content: '';
    height: 445px;
    top: 0;
    left: 0;
    right: 0;
    background: map-get($colors, bg-blue);
  }

  .services__wrapper {
    padding-left: 320px;
  }

  .services__content {
    position: relative;
    min-height: 400px;
  }

  .services__swiper-wrapper {
    display: flex;
  }

  .services__swiper {
    flex: 1;
  }

  .services__swiper-nav {
    position: relative;
    flex: 1;
    max-width: 320px;
  }

  #swiper-services-button-prev,
  #swiper-services-button-next {
    position: absolute;
    bottom: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 36px;
    height: 36px;
    padding: 0;
    border: 1px solid map-get($colors, secondary-light-gray);
    border-radius: 50%;

    cursor: pointer;
    user-select: none;
  }

  #swiper-services-button-prev {
    right: 66px;
  }

  #swiper-services-button-next {
    right: 20px;
    transform: rotate(180deg);
  }
}
</style>
