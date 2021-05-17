//할일 목록 조회 함수
<template lang="">
  <ul>
    <li v-for="(todoItem, index) in propsdata" :key="todoItem">
      {{ todoItem }}
      <button v-on:click="removeTodo(todoItem, index)">삭제</button>
    </li>
  </ul>
</template>
<script>
export default {
  //props 속성
  props: ['propsdata'],
  methods: {
    //부모 컴포넌트에 이벤트 전달
    removeTodo(todoitem, index) {
      this.$emit('removeTodo', todoitem, index);
    },
  },
};
</script>
<style lang=""></style>
