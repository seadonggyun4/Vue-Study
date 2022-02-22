<template>
  <button @click="message = 'Good?'">
    Button
  </button>
  <h1>App : {{ message }}</h1>
  <Parent />
</template>

<script>
import Parent from '~/components/ParentOne'
import {computed} from 'vue' //computed는 계산된 데이터를 만드는 함수 -> vue 패키지로부터 받아온다.

export default {
  components:{ 
    Parent
  },
  data(){
    return{
      message: 'Hello world!!'
    }
  },
  provide(){
    return{
      msg:computed(()=>{
        return this.message
      })
    }
  }
}
</script>