<template>
  <Layout>
    <h1>Category: {{ $page.category.title }} </h1>
    <ul class="post-list">
      <li v-for="post in postsInCategory" :key="post._id">
        <h2 v-html="post.node.title"/>
        <p v-html="post.node.excerpt"/>
        <router-link :to="post.node.path">Read more</router-link>
      </li>
    </ul>
  </Layout>
</template>

<page-query>
query Category ($path: String, $page: Int) {
  category: wordPressCategory (path: $path) {
    title
    slug
  }
  posts: allWordPressPost (page: $page) {
    edges {
      node {
        _id
        title
        excerpt
        path
        categories {
          slug
        }
      }
    }
  }
}
</page-query>

<script>
export default {
  computed: {
    postsInCategory: function () {
      let cat = this.$page.category.slug;
      let arr = this.$page.posts.edges;
      let newArr = arr.filter(function(item){
        return item.node.categories[0].slug === cat;
      })
      return newArr;
    }
  }
}
</script>

<style>
  .post-list {
    list-style: none;
    padding-left: 0;

  }
  .post-list li {
    padding: 1em 0;
  }
</style>