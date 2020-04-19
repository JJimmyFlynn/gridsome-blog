<template>
  <widget heading="Recent Posts">
    <ul class="sidebar-post">
      <post-card
        v-for="{ node: post } in $static.posts.edges"
        :key="post.id"
        :post="post"
      />
    </ul> <!-- End .sidebar-post -->
  </widget>
</template>

<static-query>
  query {
    posts: allContentfulBlogPost(limit: 5) {
      edges {
        node {
          id,
          title,
          slug,
          publishDate,
          heroImage {
            file {
              url
            }
          }
        }
      }
    }
  }
</static-query>

<script>
import Widget from '../Widget.vue'
import PostCard from './PostCard.vue'

export default {
  name: 'RecentPosts',
  components: {
    PostCard,
    Widget
  }
}
</script>
