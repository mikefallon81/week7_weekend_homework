<template lang="html">
  <ul v-if="article !== null">
    <li>{{article.webTitle}}</li>
  </ul>
</template>

<script>
export default {
  name: 'article-info',
  props: ['article']
}
</script>

<style lang="css" scoped>
</style>
