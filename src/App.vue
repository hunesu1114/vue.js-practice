<template>
  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }} </a>
  </div>

  <div>
    <h4 class="red" :style="스타일">{{ products[0] }}</h4>
    <p>{{ price0 }} 만원</p>
  </div>
  <div>
    <h4>{{ products[1] }}</h4>
    <p>{{ price1 }} 만원</p>
  </div>
  <div>
    <h4>{{ products[2] }}</h4>
    <p>{{ price2 }} 만원</p>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      price0: 50,
      price1: 60,
      price2: 70,
      스타일: 'color : blue',
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
      메뉴들: ['Home', 'Shop', 'About'],
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
.menu a {
  color: white;
  padding: 10px;
}
</style>
