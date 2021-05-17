<template lang="">
  <div><button type="button" v-on:click="clearTodo">전체 삭제</button></div>
</template>
<script>
export default {
  methods: {
    clearTodo() {
      //부모 컴포넌트에 이벤트 전달
      this.$emit('removeAll');
    },
  },
};
</script>
<style lang=""></style>
