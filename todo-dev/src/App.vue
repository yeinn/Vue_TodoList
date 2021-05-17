<template lang="">
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput v-on:addTodo="addTodo"></TodoInput>
    <TodoList
      v-bind:propsdata="todoItems"
      v-on:removeTodo="removeTodo"
    ></TodoList>
    <TodoFooter v-on:removeAll="clearAll"></TodoFooter>
  </div>
</template>

<script>
import TodoFooterVue from './components/TodoFooter.vue';
import TodoHeaderVue from './components/TodoHeader.vue';
import TodoInputVue from './components/TodoInput.vue';
import TodoListVue from './components/TodoList.vue';

export default {
  data() {
    return {
      //TodoList 컴포넌트에 전달할 할일 목록 데이터
      todoItems: [],
    };
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
    //TodoInput 컴포넌트에 전달할 목록 추가 함수
    addTodo(todoItem) {
      localStorage.setItem(todoItem, todoItem);
      this.todoItems.push(todoItem);
    },
    //삭제 함수
    removeTodo(todoItem, index) {
      localStorage.removeItem(todoItem);
      //index로부터 1만큼 삭제
      this.todoItems.splice(index, 1);
    },
    //리스트 전체 삭제 후 초기화 함수
    clearAll() {
      localStorage.clear();
      this.todoItems = [];
    },
  },
  components: {
    TodoHeader: TodoHeaderVue,
    TodoInput: TodoInputVue,
    TodoList: TodoListVue,
    TodoFooter: TodoFooterVue,
  },
};
</script>

<style lang=""></style>
