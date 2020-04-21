<template>
  <Layout>
    <template slot="upper">
      <section id="slider">
        <div class="style-two">
          <div class="bg-style-two">
            <div class="container">
              <div class="row">
                <div class="col-md-10 col-md-offset-1">
                  <h1>{{ $page.context.heroHeading }}</h1>
                  <h2>{{ $page.context.heroSubHeading }}</h2>
                  <p>{{ $page.context.heroBlurb }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </template>

    <post-teaser
      v-for="post in $page.posts.edges"
      :key="post.key"
      :post="post.node"
    />
  </Layout>
</template>

<page-query>
  query {
    context: contentfulPageHome(id: "u2ATPz5lOtcQdySuyjZUX") {
      heroHeading,
      heroSubHeading,
      heroBlurb
    }
    posts: allContentfulBlogPost(limit: 3) {
      edges {
        node {
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
</page-query>

<script>
import PostTeaser from '~/components/PostTeaser.vue'

export default {
  components: {
    PostTeaser
  },
  metaInfo: {
    title: 'Hello, world!'
  }
}
</script>
