<template lang="html">
  <select @change="articleSelected">
    <option selected disabled></option>
    <option v-for="(article, index) :value="index" in articles">{{article.webTitle}}</option>

  </select>
</template>

<script>
import { eventBus } from '@/main.js';


export default {
  name: 'article-select',
  props: ['articles'],
  methods: {
    articleSelected(e) {
      const selectedArticle = e.target.value;
      eventBus.$emit('article-selected', selectedArticle);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
