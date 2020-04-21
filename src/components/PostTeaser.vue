<template>
  <article class="blog-post">
    <div class="thum-item">
      <g-image
        :src="manipulateImage(post.heroImage.file.url, 'w=800')"
        alt="Post Thumnail Image"
      />
    </div> <!-- End .thum-item -->
    <div class="post">
      <div class="blog-title">
        <h2>
          <g-link :to="`/blog/${post.slug}`">
            {{ post.title }}
          </g-link>
        </h2>
      </div>
      <div class="meta">
        <ul>
          <li
            class="category"
          >
            <categories-list :categories="post.categories" />
          </li>
          <li class="author">
            By {{ post.author.name }}
          </li>
          <li class="date">
            <post-date :date-string="post.publishDate" />
          </li>
        </ul>
      </div> <!-- End .meta -->
      <div class="content">
        <p>{{ post.description }}</p>
      </div> <!-- End .content -->
      <div class="line" />
      <div class="share">
        <div class="post-bottom">
          <div class="continue">
            <g-link :to="`/blog/${post.slug}`">
              Continue Reading <span><i class="fa fa-long-arrow-right" /></span>
            </g-link>
          </div> <!-- End .continue -->
        </div> <!-- End .post-bottom -->
      </div> <!-- End .share -->
    </div> <!--  End .post -->
  </article>
</template>

<script>
import Contentful from '../mixins/Contentful.vue'
import Dates from '../mixins/Dates.vue'
import PostDate from './PostDate.vue'
import CategoriesList from './CategoriesList.vue'

export default {
  name: 'PostTeaser',
  components: {
    CategoriesList,
    PostDate
  },
  mixins: [Dates, Contentful],
  props: {
    post: {
      type: Object,
      required: true
    }
  }
}
</script>
