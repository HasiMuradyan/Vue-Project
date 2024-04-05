<script>
export default {
  props: {
    description: {
      type: String,
      required: true
    }
  }
}
</script>

<template>
  <span>{{ description }}</span>
</template>
