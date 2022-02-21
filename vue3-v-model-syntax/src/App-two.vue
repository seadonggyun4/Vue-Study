<template>
  <h1>{{ msg }}</h1>
  <!-- v-on:input은 input 태그 내부에 데이터가 하나씩 입력될때를 의미, keydown이랑은 별개 -->
  <input
    type="text"
    :value="msg"
    @input="msg = $event.target.value" />

  <h1>{{ checked }}</h1>
  <input
    type="checkbox"
    v-model="checked" />
</template>

<script>
export default {
  data(){
    return{
      msg: 'Hello world!',
      checked: false
    }
  }
}
</script>