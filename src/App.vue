<template>
  <div id="app">
    <todo-header></todo-header>
    <todo-input></todo-input>
    <todo-list></todo-list>
    <todo-footer></todo-footer>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoFooter from './components/TodoFooter.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'

export default {
  components: {
      TodoHeader,
      TodoFooter,
      TodoInput,
      TodoList,
    },
}
</script>

<style>
* {
  text-align: center;
}
li {
  list-style: none;
}
</style>
