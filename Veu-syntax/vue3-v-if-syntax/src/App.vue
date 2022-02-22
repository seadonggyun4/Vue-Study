<template>
  <button @click="handler">
    Click ME!
  </button>
  <!-- 첫번째 조건 -->
  <!-- template로 감싼 태그는 html에서 읽을때 내부 태그들만 보인다. 즉 template라는 태그는 없는것으로 취급 -->
  <template
    v-if="isShow">
    <h1>Title</h1>
    <p>hihihihihih</p>
    <p>hihihihihih</p>
  </template>
  <!-- 두번째 조건 -->
  <h1 v-else-if="count>3">
    Count > 3
  </h1>
  <!-- 마지막  -->
  <h1 v-else>
    Good~
  </h1>
  
  <!-- v-show는 내부 데이터 값의 참,거짓 여부에 상관없이 화면에서는 안보일 지라도 display:none 처리되어 태그 자체는 읽을수 있는 상태로 만든다. -->
  <!-- 즉 v-show의 경우는 항상 랜더링되어 DOM에 남아있습니다. -->
  <h1 v-show="isShow">
    v-Show
  </h1>
</template>

<script>
export default {
  data(){
    return{
      isShow:true,
      count:0,
    }
  },
  methods:{
    handler(){
      // isShow에 반대값 저장
      this.isShow = !this.isShow
      // count에 1씩 더하기
      this.count += 1
    }
  }
}
</script>