<template>
  <!-- props로 지정한 color 데이터 값을 style구문의 background 에서 사용 -->
  <!-- props로 지정한 large 데이터 값을 class로 사용 -->
  <div
    :class="{large:large}"
    :style="{backgroundColor: color}"
    class="btn">
    <!-- slot은 태그 사이에 생성되는 문자열, 태그 등 모든것을 받아주는 역할을 한다. -->
    <slot></slot>
  </div>
</template>

<script>
export default {
  // props는 component를 받아오는 App.vue 와 같은 파일에서, component를 재사용시 색상 등 의 style값을 지정하기 위함
  props:{
    //color라는 이름으로 데이터를 받아온다.
    color:{
      type:String,//String 값으로 데이터를 받아옴
      default:'gray'//기본값은 gray문자열
    },
    //large라는 이름으로 데이터를 받아온다.
    large:{
      type:Boolean,//boolean 타입으로 받는다.
      default:false // 기본값은 false
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