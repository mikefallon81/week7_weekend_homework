<template lang="html">
  <div class="main">
    <h1>News Articles</h1>
    <article-select :articles="articles" />
    <article-info :article="selectedArticle" />
  </div>
</template>

<script>
import { eventBus } from '@/main.js';
import ArticleSelect from '@/components/ArticleSelect.vue';
import ArticleInfo from '@/components/ArticleInfo.vue';


export default {
  components: {
    'article-select': ArticleSelect,
    'article-info': ArticleInfo,
  },
  data(){
    return{
      articles: [],
      selectedArticle: null,
    }
  },
  mounted(){
    eventBus.$on('article-selected', (selectedIndex) => {
      this.selectedArticle = this.articles[selectedIndex];
    });
    fetch("http://content.guardianapis.com/search?from-date=2019-08-10&to-date=2019-08-10&order-by=newest&show-fields=all&page-size=50&api-key=2b079f94-139b-4654-b363-887f8dfc9b20")



    .then(res => res.json())
    .then(articles => this.articles = articles.response.results)
  }
}
</script>

<style lang="css" scoped>
.main {
  display: ;
  padding: 10px;
}
h1 {
  width: 100%;
  display: ;
  text-align: center;
  background-color: grey;
}



</style>
