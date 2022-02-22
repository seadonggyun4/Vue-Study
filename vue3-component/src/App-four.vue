<template>
  <MyBtn>
    <template #text>
      <span>Banana</span>
    </template>
    <template #icon>
      <span>(B)</span>
    </template>
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