<template lang="html">
  <div v-if="article !== null">
    <h3>{{article.webTitle}}</h3>
    <p>{{article.sectionName}}</p>
    <p v-html="article.fields.body"></p>
</div>
</template>

<script>
export default {
  name: 'article-info',
  props: ['article']
}
</script>

<style lang="css" scoped>
</style>
