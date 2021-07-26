<template lang="pug">
  section.section.section--benefits
    .container
      .benefits__wrapper
        section-badge(absolute)
          | Выгоды
        .benefits__content
          h3.h3 Сплочённость команды профессионалов стала доступной ширнармассам
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.section--benefits {
  padding-top: 100px;

  .benefits__wrapper {
    position: relative;
    padding-left: 320px;
  }

  .benefits__content {
    max-width: 550px;
  }
}
</style>
