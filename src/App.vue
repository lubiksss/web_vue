<template>
  <div v-if="isOpened == true" class="black-bg">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="isOpened=false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="item in menu" :key="item">
      {{ item }}
    </a>
  </div>

  <div v-for="data in datas" :key="data.id">
    <img :src="data.image" alt="" class="room-img">
    <h4 @click="isOpened = true">{{ data.title }}</h4>
    <!--    <h3>{{ data.content }}</h3>-->
    <p>{{ data.price }}원</p>
  </div>
</template>

<script>
import datas from './oneroom';

export default {
  name: 'App',
  data() {
    return {
      datas: datas,
      isOpened: false,
      신고수: [0, 0, 0],
      menu: ['Home', 'Products', 'About'],
      products: ['역삼동 원룸', '천호동 원룸', '강북구 원룸']
    }
  },
  methods: {
    increase(i) {
      this.신고수[i] += 1;
    }
  },
  components: {}
}
</script>

<style>
body {
  margin: 0
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px
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
  font-size: 20px;
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

</style>
