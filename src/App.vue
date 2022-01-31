<template>

  <Modal :oneroom="oneroom" :clicked="clicked" :isOpen="isOpen"/>
  
  <div class="menu">
    <a v-for="a in menu" :key="a"> {{a}} </a>
  </div>
  
  <Discount />

  <Card :oneroom="oneroom[i]" v-for="(a, i) in oneroom" :key="a"/>

  <!-- <div>
    <img :src="oneroom[a].image" class="room-img">
    <h4 @click="isOpen = true">{{oneroom[0].title}}</h4>
    <p>{{oneroom[0].price}}</p>
    <button @click="increase0">허위매물 신고</button> <span>신고수 : {{report[0]}} </span> 
  </div> -->
  <!-- <div> 
    <img :src="oneroom[1].image" class="room-img">
    <h4 @click="isOpen = true">{{oneroom[1].title}}</h4>
    <p>{{oneroom[1].price}}</p>
    <button @click="increase1">허위매물 신고</button> <span>신고수 : {{report[1]}} </span>
  </div>
  <div>
    <img :src="oneroom[2].image" class="room-img">
    <h4 @click="isOpen = true">{{oneroom[2].title}}</h4>
    <p>{{oneroom[2].price}}</p>
    <button @click="increase2">허위매물 신고</button> <span>신고수 : {{report[2]}} </span>
  </div> -->
    
    <!-- <div v-for="(a,i) in products" :key="i">
    <h4>{{products[i]}}</h4>
    <p>70만원</p> -->
</template>

<script>

import data from './assets/oneroom.js';
import Discount from './Discount.vue';
import Modal from './Modal.vue';
import Card from './Card.vue';

export default {
  name: 'App',
  data() {
    return {
      //데이터는 object자료로 저장
      // {자료이름: 자료내용}
      clicked : 0,
      oneroom : data, 
      isOpen : false,
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      menu : ['Home', 'Products', 'About'],
      report : [0,0,0],
    };
  },

  methods : {
    // increase0() {
    //   this.report[0] += 1;
    //   //함수 안에서 데이터 사용할 때 무조건 this.써야함
    // },
    // increase1() {
    //   this.report[1] += 1;
    //   //함수 안에서 데이터 사용할 때 무조건 this.써야함
    // },  
    // increase2() {
    //   this.report[2] += 1;
    //   //함수 안에서 데이터 사용할 때 무조건 this.써야함
    // }
  },

  components : {
    Discount : Discount,
    Modal : Modal,
    Card : Card,
  },
};
</script>

<style>
body {
  margin: 0;
}

div{
  box-sizing: border-box;
}

.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;  
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: rgb(133, 193, 80);
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}


</style>
