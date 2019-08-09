<template lang="html">

</template>

<script>
export default {
  data(){
    return{
      stories: []
    }
  },
  mounted(){
    fetch("https://content.guardianapis.com/search?q=brexit&format=json&api-key=test")
    .then(res => res.json())
    .then(stories => this.stories = stories)
  }
}
</script>

<style lang="css" scoped>
</style>
