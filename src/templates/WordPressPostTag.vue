<template>
  <Layout>
    ...
  </Layout>
</template>

<graphql>
query PostTag ($path: String!) {
  wordPressPostTag (path: $path) {
    title
  }
}
</graphql>

<script>
export default {}
</script>
