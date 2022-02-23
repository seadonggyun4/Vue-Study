<template>
  <h1 @click="increase">
    {{ count }}
  </h1>
</template>

<script>
import {ref} from 'vue' //컴포지션API에 반응성을 부여하기 위해

export default {
  // data(){
  //   return{
  //     count:0
  //   }
  // },
  // methods:{
  //   increase(){
  //     this.count += 1
  //   }
  // },
  setup(){
    // let count = 0 //반응성 X
    let count = ref(0) // count는 객체데이터 -> 특정 값을 객체에서 뽑기위해 value 매서드를 사용해야 한다.
    function increase(){
      count.value += 1
    }

    return{
      count,
      increase
    }
  }
}
</script>