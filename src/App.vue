<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <div>
      <h4 class="red" :style="style1">xx원룸</h4>
      <p>{{ price1 }}만원</p>
    </div>
    <div>
      <h4>xx원룸</h4>
      <p>xx만원</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      price1: 60,
      style1: "color:red",
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
  margin-top: 60px;
}
</style>
