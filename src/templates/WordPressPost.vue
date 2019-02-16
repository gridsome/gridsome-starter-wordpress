<template>
  <Layout>
    <h1 v-html="$page.wordPressPost.title"/>
    <span>Category: </span>
    <ul>
      <li v-for="category in $page.wordPressPost.categories" :key="category.id" >
        <router-link :to="category.path">
          {{ category.slug }}
        </router-link>
      </li>
    </ul>
    <div v-html="$page.wordPressPost.content"/>
  </Layout>
</template>

<page-query>
query Post ($path: String!) {
  wordPressPost (path: $path) {
    title
    content
    categories {
      id
      slug
      path
    }
  }
}
</page-query>

<script>
export default {}
</script>
