<template>
  <div>
    <div class="menu">
      <a v-for="(menuName, i) in menuList" :key="i">{{ menuName }}</a>
    </div>
    <ModalYellow
      :원룸들="원룸들"
      :누른거="누른거"
      :isOpen="isOpen"
    ></ModalYellow
    >ModalYellow/>
    <DiscountSection></DiscountSection>

    <div v-for="(a, i) in 원룸들" :key="i">
      <img :src="a.image" class="room-image" />
      <h4
        class="red"
        :style="style1"
        @click="
          isOpen = true;
          누른거 = i;
        "
      >
        {{ a.title }}
      </h4>
      <p>{{ a.price }}원</p>
      <button @click="reportNumber[i] += 1">허위매물신고</button>
      <span>신고수 : {{ reportNumber[i] }}</span>
    </div>
  </div>
</template>

<script>
import data from "./assets/oneroom.js";
import DiscountSection from "./DiscountSection.vue";
import ModalYellow from "./ModalYellow.vue";

export default {
  name: "App",
  data() {
    return {
      누른거: 0,
      원룸들: data,
      isOpen: false,
      reportNumber: [0, 0, 0],
      price1: [60, 50, 70],
      style1: "color:red",
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      menuList: ["Home", "Shop", "About"],
    };
  },
  methods: {},
  components: {
    DiscountSection: DiscountSection,
    ModalYellow: ModalYellow,
  },
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
.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
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
