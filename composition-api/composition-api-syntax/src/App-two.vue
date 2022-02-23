<template>
  <h1 @click="increase">
    {{ count }} / {{ doubleCount }}
  </h1>
  <h1 @click="changeMessage">
    {{ message }}/ {{ reversedMessage }}
  </h1>
</template>

<script>
import {ref, computed, watch, onMounted} from 'vue'

export default {
   setup(){
      // count 관련 데이터, 컴퓨티드,매서드, 라이프사이클 훅       
      let count = ref(0)
      const doubleCount = computed(()=>{
        return count.value * 2
      })
      function increase(){
        count.value += 1
      }
       onMounted(()=>{
        console.log(count.value)
      })

      // message 관련 데이터, 컴퓨티드, 매서드, 라이프사이클 훅
      let message = ref('Hello Vue!!')
      const reversedMessage = computed(()=>{
        return message.value.split('').reverse().join('')
      })
      watch(message, (newValue)=>{
        console.log(newValue)
      })
      function changeMessage(){
        message.value = 'GOOD!!!'
      }
      console.log(message.value)


     


     return{
       count:  count,
       doubleCount,
       increase,
       message: message,
       reversedMessage,
       changeMessage,
     }
   }
}
</script>