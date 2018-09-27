<template>
  <Layout>
    <h1>Welcome to my blog :)</h1>
    <Pager :info="$page.allWordPressPost.pageInfo"/>
    <ul>
      <li v-for="{ node } in $page.allWordPressPost.edges" :key="node._id">
        <h2 v-html="node.title"/>
        <div v-html="node.fields.excerpt"/>
        <router-link :to="node.path">Read more</router-link>
      </li>
    </ul>
  </Layout>
</template>

<page-query>
query Home ($page: Int) {
  allWordPressPost (perPage: 10, page: $page) @paginate {
    pageInfo {
      totalPages
      currentPage
    }
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
</page-query>

<script>
import { Pager } from 'gridsome'

export default {
  components: {
    Pager
  }
}
</script>
