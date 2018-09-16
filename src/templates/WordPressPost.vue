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
import Layout from '@/layouts/Default.vue'

export default {
  components: {
    Layout
  }
}
</script>
