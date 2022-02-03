<template>
  <div class="black-bg" v-if="isOpen == true">
    <div class="white-bg">
      <!-- 사용자가 누른 상품 번호로 보여주기 -->
      <img :src="oneroom[clicked].image" style="width: 100%" />
      <h4>{{ oneroom[clicked].title }}</h4>
      <p>{{ oneroom[clicked].content }}</p>
      <!-- @input = 입력할 때마다 실행해주세요 라는 뜻 -->
      <!-- 유저가 입력할 때마다 month에 그 값을 저장해주세요 -->
      <input @input="month = $event.target.value">
      <p>{{month}}개월 선택함 : {{ oneroom[clicked].price * month}}원</p>
      <!-- <button @click="isOpen = false">닫기</button> -->
      <!-- props로 받아온 데이터는 read-only! -->
      <button @click="closeModal">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
    name : 'Modal',
    data() {
      return {
        month : 1,
      }
    },
    props : {
        oneroom : Object,
        clicked : Number,
        isOpen : Boolean,
    },
    methods : {
      closeModal() {
        this.$emit('closeModal')
      }
    }
};
</script>

<style>
</style>

