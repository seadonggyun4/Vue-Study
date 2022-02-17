<template>
  <button @click="add">
    ADD
  </button>
  <!-- computed 사용 -->
  <h1>{{ getterSetterMessage }}</h1>
  <h1>{{ getterSetterMessage }}</h1>
</template>

<script>
export default {
  data(){
    return{
      //getter, setter => 일반 데이터는 값을 얻어내는용도, 지정하는용도 둘다 가능하다.
      msg: 'Hello Computed!!'
    }
  },
  computed:{
    //computed는 읽기전용 데이터라 methods로 값이 변환되더라도 출력된 상태의 값이 변하진 않는다. => Getter(값을 얻어내는 용도로만 사용)
    // computed는 계산된 결과를 다시한번 호출할때 또다시 계산하지 않고 보관하고 있던 값을 리턴한다 => 캐싱
    // 캐싱 기능을 통해 데이터 최적화 가능
    reversedMessage(){
      return this.msg.split('').reverse().join('')
    },

    //computed에서도 getter, setter 가 둘다 가능한 형식으로 만들 수 있다.
    getterSetterMessage: {
      get(){
        //getter는 값을 얻어내서 화면에 보여주기때문에 만약 setter로 msg값이 변경되면 그 변경된 값을 받아 화면에 출력
        return this.msg.split('').reverse().join('')
      },
      set(newValue){
        //새로 변경된값 newValue를 msg 로 반환
        this.msg = newValue
      }
    }
  },
  methods: {
    add(){
      // this.reversedMessage += "?!"
      // this.msg += '?!'
      this.getterSetterMessage += '?!'
    }
  }
}
</script>