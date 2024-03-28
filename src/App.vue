<script>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'

export default {
  data() {
    return {
      email: '',
      isValidEmail: false
    }
  },
  methods: {
    inputEmail() {
      const input = prompt('Please enter your email:')
      if (input !== null) {
        this.email = input.trim()
        this.isValidEmail = this.validateEmail(this.email)
      }
    },
    validateEmail(email) {
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
      return emailRegex.test(email)
    },

    resetEmail() {
      this.email = ''
      this.isValidEmail = false
    }
  }
}
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
    <div
      v-if="email"
      :style="{
        border: isValidEmail ? '2px solid green' : '2px solid red'
      }"
    >
      <h1>{{ email }}</h1>
      <h4>{{ isValidEmail ? 'The email is valid' : 'The email is invalid' }}</h4>
    </div>
    <button @click="inputEmail">Input Email</button>
    <button @click="resetEmail">Reset</button>
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
