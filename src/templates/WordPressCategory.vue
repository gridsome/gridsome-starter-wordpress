<template>
  <Layout>
    <h1>Category: {{ $page.wordPressCategory.title }} </h1>
    <ul class="post-list">
      <li v-for="{ node } in $page.wordPressCategory.belongsTo.edges" :key="node.id">
        <h3 v-html="node.title" />
        <g-image :src="node.featuredMedia.url" v-if="node.featuredMedia !== null" class="post-image" />
        <div v-html="node.excerpt" />
        <g-link :to="node.path">Read More</g-link>
      </li>
    </ul>
  </Layout>
</template>

<page-query>
query Category($path: String) {
  wordPressCategory(path: $path) {
    title
    belongsTo {
      edges {
        node {
          ... on WordPressPost {
            id
          	title
            excerpt
            path
            featuredMedia {
              url
              mediaType
            }
        	}
        }
      }
    }
  }
}
</page-query>

<script>
export default {
  
}
</script>
