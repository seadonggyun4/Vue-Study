<template>
  <!-- h1클릭시 isActive 값이 false에서 true로 바뀐다.
  true로 바뀐 값에 따라 class는 active라는 클래스를 가지게 된다. 
  h1 이 isActive라는 데이터를 다루도록 v-bind라는 템플릿문법을 사용하게 되는데 이는 약어 처리되서 안보인다. -->
  <h1
    :class="{active:isActive}"
    @click="activate">
    Hello?!({{ isActive }})
  </h1>

  <!-- 스타일 바인딩은 html 태그에서 스타일을 바로 지정하는 것과 같은 역할을 한다,
  스타일 바인딩 될 데이터나 클래스 이름으로 쓰일 데이터 모두 객체 혹은 배열 과 같은 데이터로도 사용이 가능하다. -->
  <h1 :style="[styleObject, backgroundStyle]">
    style binding
  </h1>
</template>

<script>
export default {
  data(){
    return{
      isActive: false,
      styleObject:{
        color:'red',
        'font-size':"13px"
      },
      backgroundStyle:{
        backgroundColor: 'black'
      }
    }
  },
  methods: {
    activate(){
      this.isActive = true
    }
  }
}
</script>


<style lang="scss" scoped>
  .active{
    font-weight: 500;
    color: royalblue;
  }
</style>