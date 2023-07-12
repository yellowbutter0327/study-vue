<template>
  <div class="black-bg" v-if="isOpen == true">
    <div class="white-bg">
      <img :src="원룸들[누른거].image" style="width: 100%" />
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
      <p>{{ 원룸들[누른거].price }}</p>
      <!-- <button @click="isOpen = false">닫기</button> -->
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalYellow",
  props: {
    원룸들: Array,
    누른거: Number,
    isOpen: Boolean,
  },
};
</script>

<style></style>
