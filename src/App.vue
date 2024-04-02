<script>
export default {
  data() {
    return {
      mode: 'AMD -> USD',
      amdAmount: 0,
      usdAmount: 0
    }
  },
  methods: {
    convertCurrency() {
      if (this.mode === 'AMD -> USD') {
        this.usdAmount = this.amdAmount / 400
      } else {
        this.amdAmount = this.usdAmount * 400
      }
    },
    toggleMode() {
      this.mode = this.mode === 'AMD -> USD' ? 'USD -> AMD' : 'AMD -> USD'
      this.amdAmount = 0
      this.usdAmount = 0
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
    <div class="exchange-container">
      <h2>{{ mode }}</h2>
      <div v-if="mode === 'AMD -> USD'" class="input-container">
        <input type="number" v-model="amdAmount" @input="convertCurrency" class="input-field" />
        <input
          type="number"
          :value="usdAmount"
          disabled
          class="input-field"
          :class="{ disabled: true }"
        />
      </div>
      <div v-else class="input-container">
        <input type="number" v-model="usdAmount" @input="convertCurrency" class="input-field" />
        <input
          type="number"
          :value="amdAmount"
          disabled
          class="input-field"
          :class="{ disabled: true }"
        />
      </div>
      <button @click="toggleMode" class="toggle-button">Change</button>
    </div>
  </main>
</template>

<style scoped>
@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }
}
.exchange-container {
  max-width: 500px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #f0f0f0;
  border-radius: 5px;
}

.input-container {
  margin-bottom: 10px;
}
.input-field {
  width: 50%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.input-field.disabled {
  background-color: #f0f0f0;
}

.toggle-button {
  padding: 10px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.toggle-button:hover {
  background-color: #0056b3;
}
</style>
