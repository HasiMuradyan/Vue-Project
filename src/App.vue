<script>
import Product from './components/Product.vue'

export default {
  components: {
    Product
  },
  data() {
    return {
      fruits: [
        {
          name: 'apple',
          price: '3$',
          description: 'Golden apples from Armenia'
        },
        {
          name: 'pear',
          price: '300֏',
          description: 'Sweet pears'
        },
        {
          name: 'cherry',
          price: '2.6$',
          description: 'Sour red cherries'
        },
        {
          name: 'lemon',
          price: '4$',
          description: 'Big Chinese lemons'
        },
        {
          name: 'banana',
          price: '3.7$',
          description: 'Fresh bananas from Ecuador'
        }
      ],
      rate: 400
    }
  },
  methods: {
    onCurrencychange(index) {
      const fruit = this.fruits[index]
      let currentCurrency = fruit.price[fruit.price.length - 1]
      if (currentCurrency === '$') {
        fruit.price = parseFloat(fruit.price) * this.rate + '֏'
      } else {
        fruit.price = parseFloat(fruit.price) / this.rate + '$'
      }
    }
  }
}
</script>

<template>
  <main>
    <ul>
      <li v-for="(fruit, index) in fruits" :key="fruit.name">
        <Product :fruit="fruit" :index="index" @currencyChange="onCurrencychange(index)" />
      </li>
    </ul>
  </main>
</template>
