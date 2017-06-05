<template lang="html">
  <div>
    <el-menu-item index="2" v-on:click="ijinaksesdataparent">{{title.title}}</el-menu-item>
  </div>
</template>

<script>
export default {
  props: ['title'],
  methods: {
    ijinaksesdataparent(){
      this.$emit('ijinaksesdataparent')
    }
  }
}
</script>

<style lang="css">
</style>
