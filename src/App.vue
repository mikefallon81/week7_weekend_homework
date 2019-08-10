<template lang="html">
  <div>
    <article-select :articles="articles" />
    <article-info :article="selectedArticle" />
  </div>
</template>

<script>
import { eventBus } from '@/main.js';
import ArticleSelect from '@/components/ArticleSelect.vue';

export default {
  components: {
    'article-select': ArticleSelect
  },
  data(){
    return{
      articles: [],
      selectedArticle: null
    }
  },
  mounted(){
    eventBus.$on('article-selected', (selectedIndex) => {
      this.selectedArticle = this.articles[selectedIndex];
    });
    fetch("https://content.guardianapis.com/search?q=brexit&format=json&api-key=test")
    .then(res => res.json())
    .then(articles => this.articles = articles.response.results)
  }
}
</script>

<style lang="css" scoped>
</style>
