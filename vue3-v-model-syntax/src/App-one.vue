<template>
  <h1>{{ msg }}</h1>
  <!-- v-on:input은 input 태그 내부에 데이터가 하나씩 입력될때를 의미, keydown이랑은 별개 -->
  <input
    type="text"
    :value="msg" 
    @input="handler" />
</template>

<script>
export default {
  data(){
    return{
      msg: 'Hello world!'
    }
  },
  methods:{
    // handler를 통해 msg와 input은 양방향 데이터 통신을 하게 되었다
    handler(event){
      // event는 발생한 이벤트, target은 이벤트가 발생한 객체, value는 그 객체가 가지고 있는 값
      console.log(event.target.value)
      // 이벤트가 발생한 객체의 값을 msg에 대입
      this.msg = event.target.value
    }
  }
}
</script>