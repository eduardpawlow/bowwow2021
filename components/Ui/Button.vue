<template lang="pug">
  button(
    v-on="$listeners"
    :class="[variant, { rounded }]"
  )
    slot
</template>

<script>
export default {
  props: {
    rounded: {
      type: Boolean,
      default: false,
    },
    variant: {
      type: String,
      default: 'primary',
    },
  },
}
</script>
