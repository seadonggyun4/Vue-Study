<template>
  <h1 @click="changeMessage">
    {{ msg }}
  </h1>
  <h1>{{ reversedMessage }}</h1>
</template>

<script>
export default {
  data(){
    return{
      msg: 'Hello?'
    }
  },
  computed:{
    reversedMessage(){
      return this.msg.split('').reverse().join('')
    }
  },
  watch:{
    // watch는 데이터들의 변경사항이 발생했을때 감지하는 옵션
    // watch에서 생성하는 메서드는 data()중 감시할 데이터명
    // watch는 computed로 인해 변경된 message또한 감지 가능하다.
    // watch 내부의 매소드들의 매개변수는 변경된 값이다,즉 감시할 대상데이터가 변경되면 그 값이 저장되 그 값을 활용할수 있다.

    msg(){
      console.log('msg:',this.msg)
    },
    reversedMessage(changedMessage){
      console.log('reversedMessage:', changedMessage)
    }
  },
  methods: {
    changeMessage(){
      this.msg = 'Good!'
    }
  }
}
</script>