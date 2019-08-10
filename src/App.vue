<template lang="html">
  <div>
    <article-select :articles="articles" />
  </div>
</template>

<script>
import ArticleSelect from '@/components/ArticleSelect.vue';

export default {
  components: {
    'article-select': ArticleSelect
  },
  data(){
    return{
      articles: []
    }
  },
  mounted(){
    fetch("https://content.guardianapis.com/search?q=brexit&format=json&api-key=test")
    .then(res => res.json())
    .then(articles => this.articles = articles.response.results)
  }
}
</script>

<style lang="css" scoped>
</style>
