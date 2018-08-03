<template>
  <div>
    ...
  </div>
</template>

<graphql>
query Category ($path: String!) {
  wordPressCategory (path: $path) {
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
