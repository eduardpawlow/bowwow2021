<template lang="pug">
  .service-card
    .service-card__content
      .service-card__icon
        temp-service-icon
      .service-card__title
        | Неподкупность государственных СМИ
      .service-card__description.text-secondary-grey
        | Тяжёлое машиностроение - это вам не старческий скрип Амстердама

    ui-button(
      rounded
      variant="outline-primary"
      @click="$emit('click')"
    )
      | Заказать

</template>

<script>
import TempServiceIcon from '~/assets/svg/temp_service_icon.svg?inline'

export default {
  components: {
    TempServiceIcon,
  },
  props: {},
}
</script>

<style lang="scss" scoped>
.service-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 454px;
  padding: 40px 25px 50px;

  background-color: map-get($colors, bg-white);
  border-radius: 10px;
  box-shadow: 0px 20px 50px rgba(0, 0, 0, 0.1);

  &__content {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 40px;
  }

  &__icon {
    display: flex;
    margin-bottom: 30px;
  }

  &__title {
    text-align: center;
    font-weight: bold;
    font-size: 22px;
    line-height: 28px;
  }

  &__description {
    margin-top: 20px;

    text-align: center;
    font-size: 18px;
    line-height: 28px;
  }
}
</style>
