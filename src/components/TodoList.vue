<template>
  <div>
    <ul>
      <li v-for="(todoItem, index) in this.$store.state.todoItems" v-bind:key="todoItem.item">
        <span class="checkBtn" v-on:click="toggleComplete(todoItem)"><i class="fa fa-check-square" v-bind:class="{btnCompleted: todoItem.completed}"></i></span>
        <span v-bind:class="{textCompleted: todoItem.completed}">{{ todoItem.item }}</span>
        <span class="removeBtn" v-on:click="removeTodo({todoItem, index})"><i class="fas fa-trash-alt"></i></span>
      </li>
    </ul>
  </div>
</template>

<script>
import { mapMutations } from 'vuex'

export default {
  methods: {
    ...mapMutations({
      removeTodo: 'removeOneItem',
      toggleComplete: 'toggleOneItem'
    })
  },
}
</script>

<style scoped>
ul {
  padding: 0 100px;
}
li {
  box-shadow: 0 0 10px 2px rgba(0, 0, 0, .1);
  margin-top: 10px;
  line-height: 40px;
  padding-right: 10px;
}
.fa-check-square {
  width: 30px;
  height: 30px;
  float: left;
  line-height: inherit;
  color: rgb(248, 167, 174);
}
.fa-trash-alt {
  margin-left: 20px;
  float: right;
  line-height: inherit;
  color: rgb(248, 167, 174);
}
.textCompleted {
  text-decoration: line-through;
  color: rgb(197, 197, 197);
}
.btnCompleted {
  color: rgb(197, 197, 197);
}
</style>