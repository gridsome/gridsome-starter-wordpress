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
      const cat = this.$page.category.slug;
      const postsArray = this.$page.posts.edges;
      const postsArrayInCat = postsArray.filter(function(post){
        var postCats = post.node.categories;
        for (var i = 0, len = postCats.length; i < len; i++) {
          return postCats[i].slug === tag
        }
      })
      return postsArrayInCat;
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