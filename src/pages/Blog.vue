<template>
  <layout>
    <h1>Blog</h1>
    <div v-for="edge in $page.post.edges" :key="edge.node.id">
      <g-link :to="edge.node.path">{{ edge.node.title }}</g-link>
    </div>
  </layout>
</template>

<page-query>
query Post {
  post: allPost {
    edges {
      node {
        title,
        path
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: "Blog"
  }
}
</script>