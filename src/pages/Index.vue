<template>
  <Layout>

    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <g-image alt="Example image" src="~/favicon.png" width="135" />


    <div v-for="edge in $page.allPost.edges" :key="edge.node.id" class="text-blue-400">
      <h1 :id="edge.node.id" class="text-gray-400">{{ edge.node.title }}</h1>
      {{ edge.node.content }}
    </div>
    <div v-for="edge in $static.allPost.edges" :key="edge.node.id" class="text-blue-400">
      {{ edge.node.content }}
    </div>

    <p class="home-links">
      <a href="https://gridsome.org/docs/" target="_blank" rel="noopener">Gridsome Docs</a>
      <a href="https://github.com/gridsome/gridsome" target="_blank" rel="noopener">GitHub</a>
    </p>

  </Layout>
</template>
<static-query>
query {
  allPost{
    edges {
      node {
        content
      }
    }
  }
}
</static-query>
<page-query>
query {
  allPost{
    edges {
      node {
        content
        title
        id
      }
    }
  }
}
</page-query>
<script>
export default {
  metaInfo: {
    title: 'Hello, world!'
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
