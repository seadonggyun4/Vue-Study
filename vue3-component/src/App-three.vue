<template>
  <!-- html 속성표기법은 카멜케이스가 아닌 스네이크 케이스로 해야한다. -->
  <!-- donggyun 이벤트와 change-msg 이벤트가 연결되어있다. -->
  <MyBtn
    @donggyun="log"
    @change-msg="logMsg">
    Banana
  </MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'

export default {
  components:{
    MyBtn
  },
  methods:{
    log(){
      console.log('Click !!!')
      // donggyun 이라는 이름으로 이벤트를 변경했기때문에 제대로 된 값을 받기 위해서는 이벤트를 받는 컴포넌트에서 처리해줘야 한다.
      console.log(event) 
    },
    //컴포넌트로부터 받아온 msg값이 매개변수로 들어간다.  
    logMsg(msg){
      console.log(msg)
    }
  }
}
</script>