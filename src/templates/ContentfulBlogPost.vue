<template>
  <Layout>
    <div class="blog-post">
      <div class="thum-item">
        <g-image
          :src="getFeaturedImage()"
          alt="Post Thumnail Image"
        ></g-image>
      </div> <!-- End .thum-item -->
      <div class="post">
        <div class="blog-title">
          <h2>{{ $page.context.title }}</h2>
        </div>
        <div class="meta">
          <ul>
            <li class="category">
              <categories-list :categories="$page.context.categories"></categories-list>
            </li>
            <li class="author">
              By {{ $page.context.author.name }}
            </li>
            <li class="date">
              <post-date :date-string="$page.context.publishDate" />
            </li>
          </ul>
        </div> <!-- End .meta -->
        <div
          class="content"
        >
          <richtext :richtext="$page.context.content" />
        </div> <!-- End .content -->
        <div class="line" />
      </div> <!--  End .post -->
    </div> <!-- End .blog-post -->
    <div class="author-box">
      <div class="photo">
        <g-image
          :src="getAuthorImage()"
          alt="S M Mishkatul Islam"
        ></g-image>
      </div> <!-- End .photo -->
      <div class="bio">
        <h5><a href="">{{ $page.context.author.name }}</a></h5>
        <h6>{{ $page.context.author.company }}</h6>
        <p>{{ $page.context.author.shortBio }}</p>
      </div> <!-- End .bio -->
    </div> <!-- End .author-box -->
  </Layout>
</template>

<page-query>
  query Post ($path: String!) {
    context: contentfulBlogPost ( path: $path ) {
      title,
      content,
      publishDate,
      heroImage {
        file {
          url
        }
      },
      author {
        name,
        shortBio,
        company,
        image {
          file {
            url
          }
        }
      },
      categories {
        title,
        slug
      }
    }
  }
</page-query>

<script>
import Contentful from '../mixins/Contentful.vue'
import Richtext from '../components/Richtext.vue'
import Dates from '../mixins/Dates.vue';
import PostDate from '../components/PostDate.vue'
import CategoriesList from '../components/CategoriesList.vue';

export default {
  name: 'ContentfullBlogPost',
  components: {
    CategoriesList,
    Richtext,
    PostDate
  },
  mixins: [Contentful, Dates],
  methods: {
    getFeaturedImage() {
      return this.manipulateImage(this.$page.context.heroImage.file.url, '?w=800')
    },
    getAuthorImage() {
      return this.manipulateImage(this.$page.context.author.image.file.url, '?w=120')
    }
  }
}
</script>
