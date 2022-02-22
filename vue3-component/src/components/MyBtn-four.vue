<template>
  <div
    class="btn">
    <!-- slot은 태그 사이에 생성되는 문자열, 태그 등 모든것을 받아주는 역할을 한다. -->
    <!-- slot은 Fallback 컨텐츠 -> 대체 컨텐츠 -->
    <slot name="icon"></slot>
    <slot name="text"></slot>
  </div>
</template>



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