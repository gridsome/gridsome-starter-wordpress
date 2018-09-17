<template>
  <Layout>
    <h1 v-html="$page.wordPressPost.title"/>
    <div v-html="$page.wordPressPost.fields.content"/>
  </Layout>
</template>

<graphql>
query Post ($path: String!) {
  wordPressPost (path: $path) {
    title
    fields {
      content
    }
  }
}
</graphql>

<script>
export default {}
</script>
