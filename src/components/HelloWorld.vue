<template>
  <div class="container">
    <h2>This is child component</h2>
    <h3>Product list:</h3>
    <p v-for="(item, index) in products" :key="index">{{ item.name }}</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    products: {
      type: Array
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
