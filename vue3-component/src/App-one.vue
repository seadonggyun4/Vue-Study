<template>
  <MyBtn>Gray</MyBtn>
  <!-- color 데이터를 royalblue 값으로 준다 -->
  <MyBtn color="royalblue">
    Blue
  </MyBtn> 
  <MyBtn color="#000">
    Black
  </MyBtn>
  <MyBtn
    large
    color="red">
    Apple
  </MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'

export default {
  components:{
    MyBtn
  }
}
</script>