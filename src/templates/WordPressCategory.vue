<template>
  <Layout>
    ...
  </Layout>
</template>

<graphql>
query Category ($path: String!) {
  wordPressCategory (path: $path) {
    title
  }
}
</graphql>

<script>
export default {}
</script>
