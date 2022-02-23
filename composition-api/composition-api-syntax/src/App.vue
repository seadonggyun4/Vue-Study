<template>
  <MyBtn
    class="heropy"
    style="color:red"
    color="#ff0000"
    @hello="log">
    Apple
  </MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn.vue'

export default {
  components:{
    MyBtn
  },
  methods:{
    log(){
      console.log('Hello Vue!!')
    }
  }
}
</script>