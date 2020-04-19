<template>
  <article class="blog-post">
    <div class="thum-item">
      <g-image :src="manipulateImage(post.heroImage.file.url, 'w=800')" alt="Post Thumnail Image"></g-image>
    </div> <!-- End .thum-item -->
    <div class="post">
      <div class="blog-title">
        <h2><g-link :to="`/blog/${post.slug}`">{{ post.title }}</g-link></h2>
      </div>
      <div class="meta">
        <ul>
          <!--<li class="category"><a href="archive.html">Lifestyle</a></li>-->
          <li class="author">By {{ post.author.name }}</li>
          <li class="date">{{ humanReadableDate(new Date(post.publishDate), 'LLLL Lo, yyyy') }}</li>
        </ul>
      </div> <!-- End .meta -->
      <div class="content">
        <p v-html="post.description"></p>
      </div> <!-- End .content -->
      <div class="line"></div>
      <div class="share">
        <div class="post-bottom">
          <div class="continue">
            <g-link :to="`/blog/${post.slug}`">Continue Reading <span><i class="fa fa-long-arrow-right"></i></span></g-link>
          </div> <!-- End .continue -->
        </div> <!-- End .post-bottom -->
      </div> <!-- End .share -->
    </div> <!--  End .post -->
  </article>
</template>

<script>
import DateHelpers from '../mixins/DateHelpers.vue';

export default {
  name: 'PostTeaser',
  mixins: [DateHelpers],
  props: {
    post: {
      type: Object,
      required: true
    }
  },
  methods: {
    manipulateImage (imageUrl, manipulationsString) {
      return `${imageUrl}?${manipulationsString}`
    }
  }
}
</script>
