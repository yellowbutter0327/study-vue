<template>
  <div>
    <div class="menu">
      <a v-for="(menuName, i) in menuList" :key="i">{{ menuName }}</a>

      <!-- <a v-for="작명 in 반복할 횟수" :key ="작명">  -->
    </div>
    <transition name="fade">
      <ModalYellow
        :원룸들="원룸들"
        :누른거="누른거"
        :isOpen="isOpen"
        @closeModal="isOpen = false"
      ></ModalYellow>
    </transition>
    <DiscountSection v-bind="오브젝트" />
    <RoomCard
      :원룸="원룸들[i]"
      v-for="(작명, i) in 원룸들"
      @openModal="
        //부모가 메세지 수신할 때는 자식컴포넌트 골뱅이직명힌가 = 어쩌구,
        isOpen = true;
        // props로 전달되는 데이터들은 수정하면 안된다. 부모에 있는 데이터 수정하고 싶으면
        // custom event 해야한다.
        누른거 = $event;
      "
      :key="작명"
    ></RoomCard>
    <!-- 자식이 보낸 데이터는 $event 변수에 담겨 있음 -->
    <!-- 컴포넌트 : 작명 = "들어갈 내용 " -->
    <!-- 반복하려면 v-for="?? in 몇번반복할건지" :key="" -->
  </div>
  <!-- props 보낼 때 댜앙한 자료형 입력 가능하다. :작명 = "Array,Object" -->
  <!-- props 보낼때 다양한 자료형 입력 가능 
작명 = "문자자료" (콜론을 안붙이면 문자로 전달된다.), :작명 = "숫자자료" -->
</template>

<script>
// 컴포넌트 불러오고 싶을 때 import 컴포넌트 from 경로
import data from "./assets/oneroom.js";
import DiscountSection from "./DiscountSection.vue";
import ModalYellow from "./ModalYellow.vue";
import RoomCard from "./RoomCard.vue";

export default {
  name: "App",
  data() {
    return {
      오브젝트: { name: "kim", age: 20 },
      // 여기서 name, age 따로 보내고 싶으면
      // <Discount :이름 = "오브젝트.name" , 나이= "오브젝트.age"/>
      // 이렇게 할필요없이 object의 경우에는 <Discount v-bind = "오브젝트명"/>하면 된다.
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
    RoomCard: RoomCard,
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
/* 
.fade-leave-from {
  opacity: 0;
}
.fade-leave-active {
  transition: all 1s;
}
.fade-leave-to {
  opacity: 1;
} */
/* animation 주고 싶을때 class 3개 */
.fade-enter-from {
  transform: translateY(-1000px);
}
.fade-enter-active {
  transition: all 1s;
}
.fade-enter-to {
  transform: translateY(0px);
}
</style>
