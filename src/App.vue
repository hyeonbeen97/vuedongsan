<template>
  <div class="black_bg" v-if="모달창열림 == true">
    <div class="white_bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="모달창열림 = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(a, i) in 메뉴들" :key="i">{{ a }}</a>
  </div>
  <div v-for="(b, i) in 6" :key="b">
    <img
      class="room_img"
      :src="원룸들[i].image"
      alt=""
      @click="모달창열림 = true"
    />
    <h4 @click="모달창열림 = true">{{ 원룸들[i].title }} 원룸</h4>
    <p>{{ 원룸들[i].content }}</p>
    <p>{{ 원룸들[i].price }} 원</p>
  </div>
</template>

<script>
import data from "./assets/oneroom.js";

export default {
  name: "App",
  data() {
    return {
      모달창열림: false,
      신고수: [0, 0, 0],
      원룸들: data,
      메뉴들: ["Home", "Shop", "About"],
      price: [60, 70, 10],
      products: ["역삼동 ", "천호동 ", "마포구 "],
    };
  },
  methods: {
    increase() {
      this.신고수 += 1;
    },
  },
  components: {},
};
</script>

<style>
body {
  margin: 0;
}
.black_bg {
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white_bg {
  width: 100%;
  background-color: #fff;
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
  color: #fff;
  padding: 10px;
}
.room_img {
  width: 100%;
  margin-top: 40px;
}
</style>
