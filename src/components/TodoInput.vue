<template>
  <div>
    <form class="form">
    <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">
    <button class="addBtn" v-on:click="addTodo">add</button>
    </form>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      newTodoItem: ""
    }
  },
  methods: {
    addTodo: function() {
      if (this.newTodoItem !== '') {
        this.$store.commit('addOneItem', this.newTodoItem)
        this.clearInput()
      }
    },
    clearInput: function() {
      this.newTodoItem = ""
    }
  }
}
</script>

<style>
.form {
  box-shadow: 0 0 10px 2px rgba(0, 0, 0, .1);
  margin: 40px;
  height: 50px;
  line-height: 50px;
}
input {
  height: 25px;
  width: 400px;
  border: 0;
  outline: 0;
}
.addBtn {
  float: right;
  height: 50px;
  width: 50px;
  border: 0;
  background-color: rgb(248, 167, 174);
}
</style>