<template>
  <button @click="handler1">
    Click ME 1!!
  </button>
  <!-- 호출 매서드에 값이 없어도 작동이 되는것은 vue에서 제공하는 기능이기 때문이다, 통상적으로는 매서드 내부에 'hi'와 같이 값을 넣어줘야 한다. -->
  <!-- 이벤트 객체값을 같이 받고 싶을때는 $event라는 변수를 쓰면 된다 -> vue 문법 -->
  <button @click="handler2('hi', $event)">
    Click ME 2!!
  </button>

  <!-- v-on 문법으로 메서드를 여러개 연결하고 싶을때는 메서드 뒤에 반드시 ()를 붙혀야 한다!!! -->
  <button @click="handlerA(), handlerB()">
    Click ME 3!!
  </button>
</template>

<script>
export default {
  methods: {
    handler1(msg){
      console.log(msg)
      console.log(msg.target.textContent) //target은 이벤트가 발생한 객체 , textContent는 그 객체의 텍스트값
    },
    handler2(msg, event){
      console.log(msg)
      console.log(event)
    },
    handlerA(){
      console.log('A')
    },
    handlerB(){
      console.log('B')
    }
  }
}
</script>