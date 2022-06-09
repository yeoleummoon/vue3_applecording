<template>
  <div class="menu">
    <a href="javascript:void(0)" v-for="m in 메뉴들" :key="m">{{ m }}</a>
  </div>

  <div class="black-bg" v-if=" productsopen == true">
    <div class="white-bg">
       <h4>상세페이지</h4>
       <p>상세페이지 내용임</p>
       <button @click=" productsopen = false ">닫기</button>
    </div>
  </div>

  <div v-for="(list,i) in 3" :key="i">
     <h4 @click=" productsopen = true ">{{ products[i] }}</h4>
     <p>{{  price[i] }}</p>
     <button @click="reports[i]++">허위매물신고</button> <span>신고수 : {{ reports[i] }}</span>
     <!-- @click="함수명" 도 가능 -->
  </div>
 

 </template>

<script>
 
export default {
  name: 'App',
  data() {
    return {
      productsopen : false,
      reports : [0,0,0],
      메뉴들 : ['HOME', 'PRODUCTS', 'ABOUT'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      price :  ['40만원' , '50만원', '60만원']
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
div {
  box-sizing: border-box;
}
a {
  text-decoration: none;
  color: inherit;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
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
   background-color: darkslategray;
   padding: 15px;
   border-radius: 5px;

   }

.menu a {
   color: white;
   padding: 15px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;  
}
</style>
