// 할일 목록 추가함수
<template lang="">
  <div>
    <input type="text" v-model="newTodoItem" />
    <button v-on:click="addTodo">추가</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodoItem: '',
    };
  },
  methods: {
    //리스트 추가 함수
    addTodo() {
      //input 빈값 체크 (빈값이 아니라면)
      if (this.newTodoItem !== '') {
        //input 시작, 끝 공백 제거: trim()함수 사용
        var value = this.newTodoItem && this.newTodoItem.trim();

        //로컬 스토리지에 저장
        localStorage.setItem(value, value);

        //초기화
        this.clearInputbox();
      }
    },
    //초기화 함수
    clearInputbox() {
      this.newTodoItem = '';
    },
  },
};
</script>
<style lang=""></style>
