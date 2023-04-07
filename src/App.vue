<template>
  <div class="black-bg" v-if="모달창열렸니">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창열렸니 = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }} </a>
  </div>

  <!-- <div v-for="p in products" :key="p">
    <h4>
      {{ p }}
    </h4>
    <p>50 만원</p>
  </div>
   -->
  <div v-for="room in 원룸들" :key="room">
    <img :src="room.image" class="room-img" />
    <h4 @click="모달창열렸니 = true">{{ room.title }}</h4>
    <p>{{ room.price }} 만원</p>
    <!-- <button @click="increase0">허위매물신고</button>
    <span>신고수 : {{ 신고수[0] }}</span> -->
  </div>
</template>

<script>
import data from './assets/oneroom.js';

export default {
  name: 'App',
  data() {
    return {
      원룸들: data,
      모달창열렸니: false,
      신고수: [0, 0, 0],
      price0: 50,
      price1: 60,
      price2: 70,
      스타일: 'color : blue',
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
      메뉴들: ['Home', 'Shop', 'About'],
    };
  },
  methods: {
    increase0() {
      this.신고수[0]++;
    },
    increase1() {
      this.신고수[1]++;
    },
    increase2() {
      this.신고수[2]++;
    },
  },
  components: {},
};
</script>

<style>
body {
  margin: 0;
}

div {
  box-sizing: border-box;
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
.menu a {
  color: white;
  padding: 10px;
}
.room-img {
  width: 200px;
  height: 100px;
  margin-top: 40px;
}
</style>
