<template lang="pug">
  header.container
    nuxt-link(to="/").header__logo
      bowwow-logo

    nav.header__nav
      nuxt-link.header__nav-link.link(to="/" exact-path) О нас
      nuxt-link.header__nav-link.link(to="/releases") Портфолио
      nuxt-link.header__nav-link.link(to="#") Услуги
      nuxt-link.header__nav-link.link(to="#") Контакты

      ui-button(variant="primary" rounded)
        | Получить консультацию

</template>

<script>
import BowwowLogo from '~/assets/svg/bowwow-logo.svg?inline'

export default {
  components: { BowwowLogo },
}
</script>

<style lang="scss" scoped>
header {
  position: relative;
  z-index: 10;
  padding-top: 20px;
  min-height: 48px;

  display: flex;
  justify-content: space-between;
  align-items: center;

  .header__nav {
    .header__nav-link {
      display: inline-block;
      font-size: 16px;
      font-weight: 500;
      line-height: 36px;

      &.link-active {
        position: relative;

        &::after {
          content: '';
          position: absolute;
          bottom: 2px;
          left: 0;
          right: 0;
          height: 2px;
          background: map-get($colors, primary-purple);
          border-radius: 10px;
        }
      }
    }

    & > *:not(:last-child) {
      margin-right: 40px;
    }
  }
}
</style>
