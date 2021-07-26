<template lang="pug">
  section.section.section--aboutus
    .container
      .aboutus__content
        .aboutus__badge
          section-badge
            | О нас
          section-badge(src="/img/aboutus-badge1__2x.png")
          section-badge(src="/img/aboutus-badge2__2x.png")
        .aboutus__info
          h3.h3 
            | Дурное дело нехитрое: базовый вектор развития обнадёживает
          .aboutus__description.text-18.text-secondary-grey
            | Значимость этих проблем настолько очевидна, что высокое качество позиционных исследований не даёт нам иного выбора, 
            | кроме определения дальнейших направлений развития. Многие известные личности ассоциативно распределены по отраслям. 
            | Внедрение современных методик однозначно определяет каждого участника как способного принимать собственные решения 
            | касаемо распределения внутренних резервов и ресурсов. Повседневная практика показывает.
      .aboutus__partners
        .aboutus__partner
          img(src="/img/partners/nescafe.png")
        .aboutus__partner
          img(src="/img/partners/toshiba.png")
        .aboutus__partner
          img(src="/img/partners/kaspersky.png")
        .aboutus__partner
          img(src="/img/partners/microsoft.png")

      .aboutus__statistic
        .statistic__item(
          v-for="item in statistic"
          :key="item.title"
        )
          span.statistic__num.text-primary-purple
            | {{ item.number }}
          span.statistic__title.text-14.text-secondary-grey(v-html="item.title")

</template>

<script>
export default {
  data() {
    return {
      statistic: [
        {
          number: '458',
          title: 'Завершенных проектов',
        },
        {
          number: '11',
          title: 'Лет опыта в&nbsp;разработке',
        },
        {
          number: '17',
          title: 'Наград за<br>лучший проект',
        },
        {
          number: '4,9',
          title: 'Средняя оценка от&nbsp;клиентов',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.section--aboutus {
  background: map-get($colors, bg-blue);

  .aboutus__content {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .aboutus__badge {
    display: grid;
    width: 380px;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: 230px 140px;
    grid-gap: 20px;

    & ::v-deep .section-badge {
      width: auto;
      height: auto;
    }

    .section-badge:last-child {
      grid-column: 1 / 3;
    }
  }

  .aboutus__info {
    margin-left: 100px;
    max-width: 785px;

    .h3 {
      max-width: 510px;
    }

    .aboutus__description {
      margin-top: 15px;
    }
  }

  .aboutus__partners {
    display: flex;
    margin-top: 60px;

    .aboutus__partner {
      &:not(:last-child) {
        margin-right: 100px;
      }

      img {
        max-width: 220px;
      }
    }
  }

  .aboutus__statistic {
    display: flex;
    justify-content: center;
    margin-top: 20px;

    .statistic__item {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 220px;
      height: 60px;

      &:not(:last-child) {
        margin-right: 100px;
      }
    }

    .statistic__num {
      margin-right: 20px;

      font-weight: bold;
      font-size: 46px;
      line-height: 20px;
    }
  }
}
</style>
