<template lang="pug">
  section.section.section--portfolio
    .large-container
      .portfolio-grid
        card-portfolio(
          v-for="card in cards"
          :key="card.src"
          :imgSrc="card.src"
          :brand="card.brand_name"
          :class="getClassByType(card)"
        )
        card-portfolio.v-last

</template>

<script>
const mock = [
  {
    src: '/temp/img/1.png',
    brand_name: null,
    type: null,
  },
  {
    src: '/temp/img/2.png',
    brand_name: null,
    type: null,
  },
  {
    src: '/temp/img/3.png',
    brand_name: null,
    type: 'vertical',
  },
  {
    src: '/temp/img/4.png',
    brand_name: 'Brand Name',
    type: null,
  },
  {
    src: '/temp/img/5.png',
    brand_name: null,
    type: 'horizontal',
  },
  {
    src: '/temp/img/6.png',
    brand_name: 'Brand Name',
    type: 'horizontal',
  },
  {
    src: '/temp/img/7.png',
    brand_name: null,
    type: null,
  },
  {
    src: '/temp/img/8.png',
    brand_name: null,
    type: null,
  },
  {
    src: '/temp/img/9.png',
    brand_name: null,
    type: null,
  },
  {
    src: '/temp/img/10.png',
    brand_name: null,
    type: 'horizontal',
  },
  {
    src: '/temp/img/11.png',
    brand_name: 'Brand Name',
    type: null,
  },
  {
    src: '/temp/img/12.png',
    brand_name: null,
    type: null,
  },
]

export default {
  data() {
    return { cards: [] }
  },
  beforeMount() {
    let countH = 1
    let countV = 1
    this.cards = mock.map((el) => {
      if (el.type === 'horizontal') el.typeOrder = countH++
      else if (el.type === 'vertical') el.typeOrder = countV++
      else el.typeOrder = null

      return el
    })
  },
  methods: {
    getClassByType(card) {
      switch (card.type) {
        case 'horizontal':
          return `h-${card.typeOrder}`
        case 'vertical':
          return `v-${card.typeOrder}`
      }

      return ''
    },
  },
}
</script>

<style lang="scss" scoped>
.section--portfolio {
  padding-top: 60px;
  background: map-get($colors, bg-blue);

  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-auto-rows: 305px;
    grid-gap: 15px;

    .portfolio-card {
      &.v-1 {
        grid-row: 1 / 3;
        grid-column: 3;
      }

      &.v-last {
        grid-row: 2 / 4;
        grid-column: 6;
      }

      &.h-1 {
        grid-row: 1;
        grid-column: 5 / 7;
      }

      &.h-2 {
        grid-row: 2;
        grid-column: 1 / 3;
      }

      &.h-3 {
        grid-row: 3;
        grid-column: 2 / 4;
      }
    }
  }
}
</style>
