<template lang='html'>
  <div class='article' v-if='article !== null'>
    <h3>Publication: {{article.fields.publication}}</h3>
    <h3>Journalist: {{article.fields.byline}}</h3>
    <h3 class=''>Section: {{article.sectionName}}</h3>
    <p v-html='article.fields.body'></p>
</div>
</template>

<script>
export default {
  name: 'article-info',
  props: ['article']
}
</script>

<style lang="css" scoped>

h3 {
  color: grey;
  text-align: center;
}

p {
  border-style: double;
  border-color: green;
  padding: 5px;
}

</style>
