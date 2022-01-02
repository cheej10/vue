<template>
  <div class="clearAllContainter">
    <div class="clearAllBtn" v-on:click="clearAll">clear All</div>
  </div>
</template>

<script>
import { mapMutations } from 'vuex'

export default {
  methods: {
    ...mapMutations({
      clearAll: 'removeAllItem'
    })
  }
}
</script>

<style scoped>
.clearAllBtn {
  background-color: rgb(248, 167, 174);
  box-shadow: 0 0 10px 2px rgba(0, 0, 0, .1);
  margin: 40px 100px;
  line-height: 50px;
}
</style>