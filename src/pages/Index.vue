<template>
  <Layout>
    <header class="header">
      <h1>Gridsome Blog</h1>
      <p>A simple blog designed with Gridsome</p>
    </header>
    <section class="posts">
      <PostList v-for="edge in $page.allPost.edges" :key="edge.node.id" :post="edge.node" />
    </section>
  </Layout>
</template>
<script>
import PostList from "@/components/PostList";
export default {
  components: {
    PostList
  }
};
</script>
<page-query>
query {
  allPost {
    totalCount
    edges {
      node {
        id
        title
        timeToRead
        description
        date (format: "D MMMM YYYY")
        path
      }
    }
  }
}
</page-query>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
