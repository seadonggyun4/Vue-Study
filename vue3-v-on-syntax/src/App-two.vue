<template>
  <!-- 아래 a 태그와 같이 v-on 이벤트 에 붙는 메서 드 들은 vue 문법에서 기본으로 제공되는 이벤트 수식어 이다. -->
  <!-- 매서드 체이닝도 가능하다. -->

  
  <!-- prevent => 객체 기본동작 방지 -->
  <!-- once => 매서드 한번만 실행 -->
  <a
    href="https://naver.com"
    target="_blank"
    @click.prevent.once="handler">NAVER</a>
</template>

<script>
export default {
  methods:{
    handler(/*event*/){
      // event.preventDefault() // 객체 기본동작을 방지한다.
      console.log('ABC!!')
    }
  }
}
</script>