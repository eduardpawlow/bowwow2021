<template lang="pug">
  section.section.section--wellcome
    header-main
    .wellcome__content.container
      .wellcome__text
        h1.h1
          | Постоянный количественный рост продолжает удивлять
        p.text-body
          | Высококачественный прототип будущего проекта развеял последние сомнения
        .wellcome__buttons
          ui-button(variant="primary" rounded)
            | Заказать
          ui-button(variant="outline-primary" rounded)
            | Отправить ТЗ

        picture 
          // TODO <source> for webp
          img.wellcome__bg-shape(
            src="/img/shape_wellcome__1x.png"
            srcset="/img/shape_wellcome__1x.png 1x, /img/shape_wellcome__2x.png 2x"
          )
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.section.section--wellcome {
  padding-bottom: 120px;
  background: map-get($colors, bg-blue);

  .wellcome__content {
    padding-top: 215px;
    position: relative;
    height: 100%;
  }

  .wellcome__bg-shape {
    position: absolute;
    max-width: 1276px;
    top: -68px;
    right: -330px;
  }

  .wellcome__text {
    max-width: 480px;

    .text-body {
      margin-top: 20px;
    }
  }

  .wellcome__buttons {
    margin-top: 40px;

    button:not(:last-child) {
      margin-right: 20px;
    }
  }
}
</style>
