<template lang='html'>
  <div class='styled-select dropdown'>
  <select @change='articleSelected'>
  <optgroup>
  <option selected disabled></option>
    <option v-for='(article, index) in articles' :value='index'>{{article.webTitle}}</option>
  </optgroup>
    </select>
</div>
</template>

<script>
import { eventBus } from '@/main.js';


export default {
  name: 'article-select',
  props: ['articles'],
  methods: {
    articleSelected(e) {
      const selectedIndex = e.target.value;
      eventBus.$emit('article-selected', selectedIndex);
    }
  }
}
</script>

<style lang='css' scoped>

.dropdown {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #873903;
  height: 50px;
}

.styled-select select {
	font-size: 18px;
}


option {
  font-size: 28px;
}

</style>
