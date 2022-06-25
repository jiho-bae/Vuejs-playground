<template>
  <nav class="menu">
    <ul>
      <li v-for="menu in menus" :key="menu">
        <a>{{ menu }}</a>
      </li>
    </ul>
  </nav>
  <img alt="Vue logo" src="./assets/logo.png" />
  <div v-for="(product, idx) in products" v-bind:key="idx">
    <h4>{{ product.name }}</h4>
    <p>{{ product.price }} 만원</p>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      menus: ['Home', 'Shopping', 'About'],
      products: [
        { name: '역삼동 원룸', price: 60 },
        { name: '천호동 원룸', price: 40 },
        { name: '마포구 원룸', price: 50 },
      ],
    };
  },
  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu ul {
  display: flex;
  list-style: none;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
