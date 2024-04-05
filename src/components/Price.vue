<script>
export default {
  props: {
    price: {
      type: String,
      required: true
    }
  }
}
</script>

<template>
  <span>{{ price }}</span>
</template>
