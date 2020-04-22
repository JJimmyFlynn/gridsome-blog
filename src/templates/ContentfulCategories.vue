<template>
  <Layout>
    <template slot="upper">
      <section
        id="page-title"
        class="page-title"
      >
        <div class="bg-title">
          <div class="container">
            <div class="title">
              <h1>Category: {{ $page.context.categoryTitle }}</h1>
            </div><!-- End .title -->
          </div> <!-- End .container -->
        </div>
      </section>
    </template>

    <post-teaser
      v-for="post in $page.context.belongsTo.edges"
      :key="post.key"
      :post="post.node"
    />
  </Layout>
</template>

<page-query>
  query Category ($path: String!) {
    context: contentfulCategories(path: $path) {
      categoryTitle: title,
      belongsTo {
        edges {
          node {
            ... on ContentfulBlogPost {
              id,
              slug,
              title,
              author {
                name
              },
              publishDate,
              description,
              heroImage {
                file {
                  url,
                }
              },
              categories {
                title,
                slug
              }
            }
          }
        }
      }
    }
  }
</page-query>

<script>
import PostTeaser from '../components/PostTeaser.vue';

export default {
  name: 'ContentfulCategory',
  components: {
    PostTeaser
  },
  metaInfo () {
    return {
      title: `${this.$page.context.categoryTitle} Archives`
    }
  },
}
</script>
