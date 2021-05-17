<template lang="">
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput></TodoInput>
    <TodoList></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
import TodoFooterVue from './components/TodoFooter.vue';
import TodoHeaderVue from './components/TodoHeader.vue';
import TodoInputVue from './components/TodoInput.vue';
import TodoListVue from './components/TodoList.vue';

export default {
  components: {
    TodoHeader: TodoHeaderVue,
    TodoInput: TodoInputVue,
    TodoList: TodoListVue,
    TodoFooter: TodoFooterVue,
  },
};
</script>

<style lang=""></style>
