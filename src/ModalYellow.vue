<template>
  <div class="black-bg" v-if="isOpen == true">
    <div class="white-bg">
      <img :src="원룸들[누른거].image" style="width: 100%" />
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
      <input @input="month = $event.target.value" />
      <input v-model.number="month" />
      <p>{{ month }}개월 선택함 : {{ 원룸들[누른거].price * month }}</p>

      <button @click="close">닫기</button>
    </div>
  </div>
</template>

<!-- 사용자가 입력한 값을 month에 저장해 달라. -->
<!-- // input에 거는 이벤트 input은 작성될때마다 검사, change는 커서 다른데 찍으면
실행하는거 -->
<!-- input 위에랑 아래랑 같은 기능임 입력한 값을 모두 데이터로 저장하는 방법이다. -->
<!-- textarea나 select 에도 동일하게 v-model적용할 수 있다. -->

<script>
export default {
  name: "ModalYellow",
  data() {
    return {
      month: 1,
      //사용자가 input에 입력한 것은 전부 문자자료형이다.
      // 초기값도 은근 중요한게 input에 문자가 오면 문자 적어줘야.
      // 빈 문자는 ''
      // 숫자가 들어가야할때는 v-model.number 위처럼
    };
  },
  props: {
    원룸들: Array,
    누른거: Number,
    isOpen: Boolean,
  },
  methods: {
    close() {
      this.$emit("closeModal");
    },
  },
};
</script>

<style></style>
