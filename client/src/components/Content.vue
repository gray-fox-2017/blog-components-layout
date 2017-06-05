<template lang="html">
  <div>
    <p>{{detail.title}} - {{detail.content}}</p>
    <p>By: {{detail.author.name}}</p>
  </div>
</template>

<script>
export default {
  props: ['detail']
}
</script>

<style lang="css">
</style>
