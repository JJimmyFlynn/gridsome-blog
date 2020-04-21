<template>
  <li
    class="item"
  >
    <div class="thum-img">
      <g-image
        :src="getThumbnail()"
        alt="Small Thumbnail Image"
      />
    </div> <!-- End .thum-img -->
    <div class="post-meta">
      <h4>
        <g-link :to="`/blog/${post.slug}`">
          {{ post.title }}
        </g-link>
      </h4>
      <p><post-date :date-string="post.publishDate" /></p>
    </div> <!-- End .post-meta -->
  </li> <!-- End .item -->
</template>

<script>
import Contentful from '../../mixins/Contentful.vue'
import Dates from '../../mixins/Dates.vue'
import PostDate from '../PostDate.vue'

export default {
  name: 'PostCard',
  components: {
    PostDate
  },
  mixins: [Contentful, Dates],
  props: {
    post: {
      type: Object,
      required: true
    }
  },
  methods: {
    getThumbnail () {
      return this.manipulateImage(this.post.heroImage.file.url, 'w=100&h=100&fit=fill')
    }
  }
}
</script>
