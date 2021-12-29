<template>
  <div>
    <ul>
      <li v-for="(todoItem, index) in this.$store.state.todoItems" v-bind:key="todoItem.item">
        <span class="checkBtn" v-on:click="toggleComplete(todoItem)">V</span>
        <span v-bind:class="{textCompleted: todoItem.completed}">{{ todoItem.item }}</span>
        <span class="removeBtn" v-on:click="removeTodo({todoItem, index})">X</span>
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
.textCompleted {
  text-decoration: line-through;
  color: black;
}
</style>