<template>
  <Layout>
    <h1 v-html="$page.wordPressPost.title"/>
    <h4>Posted in:</h4>
    <ul class="categories-list">
      <li v-for="category in $page.wordPressPost.categories" :key="category.id" >
        <router-link :to="category.path">
          {{ category.title }}
        </router-link>
      </li>
    </ul>
    
    <div v-html="$page.wordPressPost.content"/>
    <h4>Tags:</h4>
    <ul class="tags-list">
      <li v-for="tag in $page.wordPressPost.tags" :key="tag.id" >
        <router-link :to="tag.path">
          {{ tag.title }}
        </router-link>
      </li>
    </ul>
  </Layout>
</template>

<page-query>
query Post ($path: String!) {
  wordPressPost (path: $path) {
    title
    content
    categories {
      id
      title
      path
    }
    tags {
      id
      title
      path
    }
  }
}
</page-query>

<script>
export default {}
</script>

<style>
  ul.tags-list,
  ul.categories-list {
    list-style: none;
    padding: 0;
    display: flex;
    flex-direction: row;
  }
  ul.tags-list li a,
  ul.categories-list li a {
    padding: 0 1em;
    display: inline-block;
  }
  ul.tags-list li:first-child a,
  ul.categories-list li:first-child a {
    padding-left: 0;
  }
  ul.tags-list li:after {
    content: '|';
    display: inline-block;
  }
  ul.categories-list li:after {
    content: ',';
    display: inline-block;
  }
  ul.tags-list li:last-child:after,
  ul.categories-list li:last-child:after {
    content: '';
  }
</style>
