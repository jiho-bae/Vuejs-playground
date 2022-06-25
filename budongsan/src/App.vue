<template>
  <div class="black-bg" v-if="modalOpened">
    <div class="white-bg">
      <button @click="toggleModal">모달 닫기</button>
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
    </div>
  </div>

  <nav class="menu">
    <ul>
      <li v-for="menu in menus" :key="menu">
        <a>{{ menu }}</a>
      </li>
    </ul>
  </nav>
  <button @click="toggleModal">모달 열기</button>
  <div v-for="room in dummy" :key="room.id">
    <img class="my-image" :src="room.image" />
    <h4>{{ room.title }}</h4>
    <span>${{ room.price }}</span>
  </div>

  <div v-for="(product, idx) in products" :key="idx">
    <img class="my-image" src="./assets/img1.jpeg" />
    <h4>{{ product.name }}</h4>
    <p>{{ product.price }} 만원</p>
    <button @click="increase(idx)">허위매물 신고</button>
    <span>신고 수 : {{ report[idx] }}</span>
  </div>
</template>

<script>
import dummy from './assets/dummy';

export default {
  name: 'App',
  data() {
    return {
      report: [0, 0, 0],
      menus: ['Home', 'Shopping', 'About'],
      modalOpened: false,
      products: [
        { name: '역삼동 원룸', price: 60 },
        { name: '천호동 원룸', price: 40 },
        { name: '마포구 원룸', price: 50 },
      ],
      dummy,
    };
  },
  methods: {
    increase: function (idx) {
      this.report[idx] += 1;
    },
    decrease(idx) {
      this.report[idx] -= 1;
    },
    toggleModal() {
      this.modalOpened = !this.modalOpened;
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
.my-image {
  width: 200px;
  height: 200px;
  margin-top: 40px;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
