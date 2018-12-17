<template>
  <Layout>
    <h1 v-html="$page.wordPressPostTag.title"/>
  </Layout>
</template>

<page-query>
query Category ($path: String!) {
  wordPressCategory (path: $path) {
    title
  }
}
</page-query>

<script>
export default {}
</script>
