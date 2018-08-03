<template>
  <Layout>
    <h1>Welcome to my blog :)</h1>
    <ul>
      <li v-for="{ node } in $page.allWordPressPost.edges" :key="node._id">
        <h2 v-html="node.title"/>
        <div v-html="node.fields.excerpt"/>
        <router-link :to="node.path">Read more</router-link>
      </li>
    </ul>
  </Layout>
</template>

<graphql>
query Home {
  allWordPressPost {
    edges {
      node {
        _id
        title
        path
        fields {
          excerpt
        }
      }
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
