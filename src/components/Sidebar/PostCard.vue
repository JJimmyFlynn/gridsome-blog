<template>
  <li
    class="item"
  >
    <div class="thum-img">
      <g-image
        :src="getThumbnail(post.heroImage.file.url)"
        alt="Small Thumbnail Image"
      />
    </div> <!-- End .thum-img -->
    <div class="post-meta">
      <h4>
        <g-link :to="`/blog/${post.slug}`">
          {{ post.title }}
        </g-link>
      </h4>
      <p>{{ humanReadableDate(new Date(post.publishDate), 'LLLL Lo, yyyy') }}</p>
    </div> <!-- End .post-meta -->
  </li> <!-- End .item -->
</template>

<script>
import Contentful from '../../mixins/Contentful.vue'
import Dates from '../../mixins/Dates.vue'

export default {
  name: 'PostCard',
  props: {
    post: {
      type: Object,
      required: true
    }
  },
  mixins: [Contentful, Dates],
  methods: {
    getThumbnail (imageUrl) {
      return this.manipulateImage(imageUrl, 'w=100&h=100&fit=fill')
    }
  }
}
</script>
