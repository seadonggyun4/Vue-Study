<template>
  <div
    class="btn"
    v-bind="$attrs">
    <!-- slot은 태그 사이에 생성되는 문자열, 태그 등 모든것을 받아주는 역할을 한다. -->
    <slot></slot>
  </div>
  <h1></h1>
</template>

<script>
export default {
  inheritAttrs: false,
  created(){
    console.log(this.$attrs)
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