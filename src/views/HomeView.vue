<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <counter />
    <counter-squared />
    <div class="buttons">
      <button @click="$store.dispatch('decreaseCounter')">-</button>
      <button @click="$store.dispatch('increaseCounter')">+</button>
    </div>
    <div>
      <input type="text" name="" id="" placeholder="Enter color code"
              v-model="colorCode"
      >
    </div>
  </div>
</template>

<script>

export default {
  name: 'HomeView',
  computed: {
    colorCode: {
      get() {
        return this.$store.state.colorCode
      },
      set(newValue) {
        this.$store.commit('setColorCode', newValue)
      }
    }
  },
  components: {
    'counter': require('@/components/Counter.vue').default,
    'counter-squared': require('@/components/CounterSquared.vue').default

  }
}
</script>
<style>
div {
  margin-bottom: 10px;
}
.counter {
  font-size: 80px;
}
.buttons button {
  font-size: 40px;
  width: 100px;
  margin: 0 10px;
}
</style>