<template>
  <div
    class="btn">
    <!-- slot은 태그 사이에 생성되는 문자열, 태그 등 모든것을 받아주는 역할을 한다. -->
    <slot></slot>
  </div>
  <!-- dblclick은 더블클릭 이벤트 이다. -->
  <h1 @dblclick="$emit('donggyun'), $event">
    ABC
  </h1>
  <!-- msg데이터를 양방향 통신으로 받게끔 만든다. -->
  <input
    type="text"
    v-model="msg" />
</template>

<script>
export default {
  emits:[
    'donggyun',
    'changeMsg'
  ],
  data(){
    return{
      msg: ''
    }
  },
  watch:{
    // msg 데이터가 수정될때마다 감시하고 ,emit에서 changMsg라는 이벤트를 발생시키고, msg 값을 받아온다.
    msg(){
      this.$emit('changeMsg', this.msg)
    }
  }
}
</script>


<style scoped lang="scss">
  .btn{
    display: inline-block;
    margin:4px;
    padding: 6px 12px;
    border-radius: 4px;
    background-color: gray;
    color: white;
    cursor: pointer;

    &.large{
      padding: 10px 20px;
      font-size: 20px;
    }
  }


</style>