<template>
  <!-- 컴포넌트 태그에 ref사용 -->
  <Hello ref="hello" />
</template>

<script>
import Hello from '~/components/HelloOne'
export default {
  components:{
    Hello
  },
  mounted(){
    const HelloEl = this.$refs.hello.$refs.good
    console.log(HelloEl)
  }
}
</script>