<template>
  <div id="app">
    <p v-bind:class="count % 2 === 0 ? 'show' : 'hidden'">{{ count }}</p>
    <input v-if="inputType === 'text'" type="text">
    <input v-else type="date">
    <button @click="showInput">{{ inputType === 'text' ? 'Text' : 'Date time' }}</button>
    <div class="loop">
      <p v-for="(item, index) in products" :key="index">{{ item.name }}</p>
    </div>
    <input type="text" v-model="product" />
    <button @click="submitProduct">Submit</button>
    <HelloWorld :products="products" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
export default {
  name: 'App',
  components: { HelloWorld },
  data() {
    return {
      product: '',
      product1Way: '',
      products: [
        { id: 1, name: 'milk' },
        { id: 2, name: 'rice' },
        { id: 3, name: 'laptop' },
        { id: 4, name: 'fruit' },
        { id: 5, name: 'beverage' },
      ],
      message: 'Count message',
      count: 3,
      isShow: true,
      inputType: 'text',
    }
  },
  methods: {
    submitProduct() {
      console.log(this.product)
    },
    showPassword() {
      this.isShow = !this.isShow
    },
    countUp() {
      return this.count + 2
    },
    showInput() {
      if (this.inputType === 'text') {
        this.inputType = 'datetime'
      } else {
        this.inputType = 'text'
      }
    },
  },
}
</script>

<style scoped>
#app {
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
  align-items: center;
}

.show {
  display: block;
}

.hidden {
  display: none
}
</style>
