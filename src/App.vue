<template>
  <section>
<div class="black-bg" v-if="modal == true">
  <div class="white-bg">
    <h4>{{data[1].title}}</h4>
    <img src="./assets/seonghyeon.png" alt="1" class="room-img">
    <p>{{data[1].content}}</p>
    <button @click="modal = false" >모달 닫기</button>
  </div>
</div>

<div>
<div class="modal-overlay" v-if="modalOpen" @click="closeModal">
  <div class="modal">
    <img src="./assets/seonghyeon.png" alt="1" class="room-img">
    <button  @click="closeModal">모달 닫기</button>

  </div>

</div>
</div>

  <div class="menu">
    <a v-for="a in menus" :key="a" > {{ a }} </a>
  </div>
  
  <div>
   
   <h4 class="red" :style="style1"> {{ price1 }} 원룸 </h4>
   <P> {{ price2 }} 원룸 </P>

   <div> 
    <img src="./assets/seonghyeon.png" alt="1" class="room-img">
    <button @click="modal = true">모달 열기</button>
    <P> {{ product[0] }} 원룸ssss </P>
    <button @click="신고수[0]++">허위매물신고</button> <span>신고수 : {{신고수[0] }}</span>
    
   </div>

      <div>
    <img src="./assets/seonghyeon.png" alt="1" class="room-img">
    <h4> {{data[0].title}}</h4>
    <P> {{data[0].price}} </P>
    <P> {{data[0].content}} </P>
    <P> {{data[0].image}} </P>
    <button @click="openModal">모달 열기</button>
   </div>
  
  <div>
  <img src="./assets/seonghyeon.png" alt="1" class="room-img">
  <P> {{ product[1] }} 원룸 </P>
  <button @click="신고수[1]++">허위매물신고2</button>  <span>두번째 신고수 : {{신고수[1]}} </span>

  </div>
 

   
   
  </div>
  </section>
</template>

<script>

import post from './data/post.js'


export default {
  name: 'App',
  data() {
    return{
      modalOpen : false,
      data : post,
      modal : false,
      신고수 : [0,0,0],
      menus : ['home', 'shop', 'about'],
      price1 : 60,
      price2 : 70,
      style1: 'color:blue',
      product : ['역삼동', '천호동', '마포구'],
      

    }
  },
  methods : {

    openModal(){
      this.modalOpen = true;
    },
    closeModal(){
      this.modalOpen = false;
    },

    increase(){
      this.신고수 += 1;
    },
    increase2(){
      this.신고수 += 1;
    }
  },
  components: {
    
  }
}
</script>

<style>
body {
  margin: 0;
}

div{
  box-sizing: border-box;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: #ffffff;
  border-radius: 8px;
  padding: 20px;
}

.modal {
  width: 100%;
  background: #ffffff;
  border-radius: 8px;
  padding: 20px;
}

.modal-overlay{
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}



#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
}

.menu{
  background: blueviolet;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
.room-img {
  width: 100px;
  margin-top: 10px;
}

</style>

