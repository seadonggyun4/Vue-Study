<template>
  <input
    type="text"
    @keydown.ctrl.shift.a="handler" />
</template>

<script>
export default {
  methods: {
    handler(){
      console.log('Enter !!!')
    }
  }
}
</script>