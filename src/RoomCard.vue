<template>
  <div>
    <img :src="원룸.image" class="room-image" />
    <h4 @click="send">
      {{ 원룸.title }}
    </h4>
    <!-- click 옆에 있는 게 너무 길면 methods로 분리해서 사용 -->

    <p>{{ 원룸.price }}원</p>
  </div>
</template>

<script>
export default {
  props: {
    원룸: Object, // 원룸이라는 데이터를 받아왔으니 원룸이라고 적어준다.
  },
  methods: {
    send() {
      this.$emit("openModal", this.원룸.id);
    }, //자료가 부모까지 전달이 된다.
    //emit 함수 안에서 하고 싶으면 props, data, 변수에서 갖고 싶으먼 this 붙이기
  },
};

// <!-- 자식이 부모 요소 건드려 event 발생시키고 싶을 때
// custom event 사용한다. -->
// 부모에게 메세지 보낼때는 $emit('작명', 데이터)
// 부모가 수신 받을 때는 @작명한 이름 = "모달창열렸니 = true"
</script>

<style></style>
