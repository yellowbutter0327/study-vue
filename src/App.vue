<template>
  <div>
    <div class="black-bg" v-if="isOpen == true">
      <div class="white-bg">
        <h4>상세페이지임</h4>
        <p>상세페이지 내용임</p>
        <button @click="isOpen = false">닫기</button>
      </div>
    </div>

    <div class="menu">
      <a v-for="(menuName, i) in menuList" :key="i">{{ menuName }}</a>
    </div>

    <div>
      <img :src="원룸들[0].image" class="room-img" />
      <h4 class="red" :style="style1" @click="isOpen = true">
        {{ 원룸들[0].title }}
      </h4>
      <p>{{ 원룸들[0].price }}원</p>
      <button @click="reportNumber[0] += 1">허위매물신고</button>
      <span>신고수 : {{ reportNumber[0] }}</span>
    </div>

    <div>
      <img :src="원룸들[1].image" class="room-img" />
      <h4 class="red" :style="style1" @click="isOpen = true">
        {{ 원룸들[1].title }}
      </h4>
      <p>{{ 원룸들[1].price }}원</p>
      <button @click="reportNumber[1] += 1">허위매물신고</button>
      <span>신고수 : {{ reportNumber[1] }}</span>
    </div>

    <div>
      <img :src="원룸들[2].image" class="room-img" />
      <h4 class="red" :style="style1" @click="isOpen = true">
        {{ 원룸들[2].title }}
      </h4>
      <p>{{ 원룸들[2].price }}원</p>
      <button @click="reportNumber[2] += 1">허위매물신고</button>
      <span>신고수 : {{ reportNumber[2] }}</span>
    </div>

    <div>
      <img :src="원룸들[3].image" class="room-img" />
      <h4 class="red" :style="style1" @click="isOpen = true">
        {{ 원룸들[3].title }}
      </h4>
      <p>{{ 원룸들[3].price }}원</p>
    </div>

    <div>
      <img :src="원룸들[4].image" class="room-img" />
      <h4 class="red" :style="style1" @click="isOpen = true">
        {{ 원룸들[4].title }}
      </h4>
      <p>{{ 원룸들[4].price }}원</p>
    </div>

    <div>
      <img :src="원룸들[5].image" class="room-img" />
      <h4 class="red" :style="style1" @click="isOpen = true">
        {{ 원룸들[5].title }}
      </h4>
      <p>{{ 원룸들[5].price }}원</p>
    </div>
  </div>
</template>

<script>
import data from "./assets/oneroom.js";

export default {
  name: "App",
  data() {
    return {
      원룸들: data,
      isOpen: true,
      reportNumber: [0, 0, 0],
      price1: [60, 50, 70],
      style1: "color:red",
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      menuList: ["Home", "Shop", "About"],
    };
  },
  methods: {},
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
  width: 100%;
  margin-top: 40px;
}
</style>
