<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import { ref } from 'vue'
let count = ref(0);

const decreaseByTen = () => {
      count.value -= 10;
    };

const decreaseByOne = () => {
      count.value--;
    };

const increaseByOne = () => {
      count.value++;
    };

const increaseByTen = () => {
      count.value += 10;
    };
 const reset = () => {
      count.value = 0;
    };


</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />
    <button @click="decreaseByTen()">-10</button>
    <button @click="decreaseByOne()">-1</button>
    <span>{{count}}</span>
    <button @click="increaseByOne()">1</button>
    <button @click="increaseByTen()">10</button>
    <button @click="reset()">Reset</button>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
