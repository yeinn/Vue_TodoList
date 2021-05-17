//할일 목록 조회 함수
<template lang="">
  <ul>
    <li v-for="(todoItem, index) in todoItems" :key="todoItem">
      {{ todoItem }}
      <button v-on:click="removeTodo(todoItem, index)">삭제</button>
    </li>
  </ul>
</template>
<script>
export default {
  data() {
    return { todoItems: [] };
  },
  // created: data 속성과 methods 속성 정의 이후 실행되는 단계
  created() {
    if (localStorage.length > 0) {
      for (var i = 0; i < localStorage.length; i++) {
        //웹팩 데브 서버 제외 (개발모드)
        if (localStorage.key(i) != 'loglevel:webpack-dev-server') {
          this.todoItems.push(localStorage.key(i));
        }
      }
    }
  },
  methods: {
    //삭제기능
    removeTodo(todoItem, index) {
      localStorage.removeItem(todoItem);
      //index로부터 1만큼 삭제
      this.todoItems.splice(index, 1);
    },
  },
};
</script>
<style lang=""></style>
