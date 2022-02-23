<template>
  <div
    v-bind="$attrs"
    class="btn"
    @click="hello">
    <slot></slot>
  </div>
</template>

<script>
import {onMounted} from 'vue'

export default {
  inheritAttrs:false,
  props:{
    color:{
      type:String,
      default:'gray'
    }
  },
  emits: ['hello'],
  setup(props, context){
    //사용할 매서드
    function hello(){
      context.emit('hello')
    }

    //사용할 라이프 사이클 훅
    onMounted(()=>{
      console.log(props.color)
      console.log(context.attrs)
    })

    //리턴값
    return{
      hello
    }
  }
}
</script>