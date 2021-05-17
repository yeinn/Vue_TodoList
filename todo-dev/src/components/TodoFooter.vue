<template lang="">
  <div><button type="button" v-on:click="clearTodo">전체 삭제</button></div>
</template>
<script>
export default {
  methods: {
    clearTodo() {
      localStorage.clear();
    },
  },
};
</script>
<style lang=""></style>
