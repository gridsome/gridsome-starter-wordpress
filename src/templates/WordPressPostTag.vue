<template>
  <div>
    ...
  </div>
</template>

<graphql>
query PostTag ($path: String!) {
  wordPressPostTag (path: $path) {
    title
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
