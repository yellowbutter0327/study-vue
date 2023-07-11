<template>
  <div>
    <div class="menu">
      <a v-for="(menuName, i) in menuList" :key="i">{{ menuName }}</a>
    </div>
    <div v-for="(roomName, i) in roomList" :key="i">
      <h4 class="red" :style="style1">{{ roomName }}</h4>
      <p>{{ price1[i] }}만원</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      price1: [60, 50, 70],
      style1: "color:red",
      roomList: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      menuList: ["Home", "Shop", "About"],
    };
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
