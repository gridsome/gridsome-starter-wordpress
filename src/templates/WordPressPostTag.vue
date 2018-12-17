<template>
  <Layout>
    <h1 v-html="$page.wordPressPostTag.title"/>    
  </Layout>
</template>

<page-query>
query PostTag ($path: String!) {
  wordPressPostTag (path: $path) {
    title
  }
}
</page-query>

<script>
export default {}
</script>
