<script>
export default {
  props: {
    name: {
      type: String,
      required: true
    }
  }
}
</script>

<template>
  <span>{{ name }}</span>
</template>
