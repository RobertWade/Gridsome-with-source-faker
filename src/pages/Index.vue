<template>
  <Layout>
    <div class="content">
      <div class="card" v-for="edge in $page.allFaker.edges" :key="edge.node.id">
        <div class="card-content columns">
        <div class="column is-2">
          <figure class="image is-128x128">
            <img class="is-rounded" :src="edge.node.avatar">
          </figure>
        </div>
        <div class="column">
          <p class="title"> {{ edge.node.author }}</p>
          <p class="subtitle"> <i class="has-text-dark">Contact Email:</i> {{ edge.node.email.src }}</p>
          <p class="subtitle"> <i class="has-text-dark"> Profile: </i> {{ edge.node.title }}</p>
        </div>
        </div>
      </div>
    </div>
  </Layout>
</template>

<page-query>
query allFaker {
  allFaker (perPage: 10) {
    edges {
      node {
        email,
        author,
        avatar,
        title,
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
