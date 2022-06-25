<template>
  <nav class="menu">
    <ul>
      <li v-for="menu in menus" :key="menu">
        <a>{{ menu }}</a>
      </li>
    </ul>
  </nav>
  <img alt="Vue logo" src="./assets/logo.png" />
  <div>
    <h4>{{ products[0].name }}</h4>
    <p>{{ products[0].price }} 만원</p>
    <button @click="report++" @mouseover="report += 3">허위매물 신고</button>
    <button @click="increase">증가</button>
    <button @click="decrease">감소</button>
    <span>신고 수 : {{ report }}</span>
  </div>
  <div>
    <h4>{{ products[1].name }}</h4>
    <p>{{ products[1].price }} 만원</p>
  </div>
  <div>
    <h4>{{ products[2].name }}</h4>
    <p>{{ products[2].price }} 만원</p>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      report: 0,
      menus: ['Home', 'Shopping', 'About'],
      products: [
        { name: '역삼동 원룸', price: 60 },
        { name: '천호동 원룸', price: 40 },
        { name: '마포구 원룸', price: 50 },
      ],
    };
  },
  methods: {
    increase: function () {
      this.report += 3;
    },
    decrease() {
      this.report -= 3;
    },
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
