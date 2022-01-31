<template>
  <div class="black-bg" v-if="isOpen == true">
    <div class="white-bg">
      <!-- 사용자가 누른 상품 번호로 보여주기 -->
      <img :src="oneroom[clicked].image" style="width: 100%" />
      <h4>{{ oneroom[clicked].title }}</h4>
      <p>{{ oneroom[clicked].content }}</p>
      <p>{{ oneroom[clicked].price }}원</p>
      <!-- <button @click="isOpen = false">닫기</button> -->
      <!-- props로 받아온 데이터는 read-only! -->
    </div>
  </div>
</template>

<script>
export default {
    name : 'Modal',
    props : {
        oneroom : Object,
        clicked : Number,
        isOpen : Boolean,
    }
};
</script>

<style>
</style>

