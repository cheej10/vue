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

<style>

</style>