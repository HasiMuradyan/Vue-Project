<script>
import Name from './Name.vue'
import Price from './Price.vue'
import Description from './Description.vue'
export default {
  components: {
    Name,
    Price,
    Description
  },
  props: {
    fruit: {
      type: Object,
      required: true
    }
  },
  methods: {
    onButtonClick() {
      this.$emit('currencyChange')
    }
  }
}
</script>

<template>
  <div>
    <Name :name="fruit.name" /> <Price :price="fruit.price" /><button @click="onButtonClick">
      Change the currency
    </button>
    <Description :description="fruit.description" />
  </div>
</template>
