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
        <div class="share">
          <div class="post-bottom">
            <div class="tag">
              <span>Tag:</span>
              <a href="#">lifestyle</a>
              <a href="#">music</a>
              <a href="#">rock</a>
            </div> <!-- End .continue -->
            <div class="share-iocn">
              <span class="share">Share:</span>
              <span class="icon"><a href="#"><i class="fa fa-facebook" /></a></span>
              <span class="icon"><a href="#"><i class="fa fa-twitter" /></a></span>
              <span class="icon"><a href="#"><i class="fa fa-google-plus" /></a></span>
              <span class="icon"><a href="#"><i class="fa fa-pinterest" /></a></span>
            </div> <!-- End .share-iocn -->
          </div> <!-- End .post-bottom -->
        </div> <!-- End .share -->
      </div> <!--  End .post -->
    </div> <!-- End .blog-post -->
    <div class="author-box">
      <div class="photo">
        <a href="#"><img
          src="images/author.jpg"
          alt="S M Mishkatul Islam"
        ></a>
      </div> <!-- End .photo -->
      <div class="bio">
        <h5><a href="">S M Mishkatul islam</a></h5>
        <h6>web designer and developer</h6>
        <p>Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Sed ut perspiciatis unde omnis iste natus error sit aperiam.</p>
        <div class="share-iocn">
          <span class="icon"><a href="#"><i class="fa fa-facebook" /></a></span>
          <span class="icon"><a href="#"><i class="fa fa-twitter" /></a></span>
          <span class="icon"><a href="#"><i class="fa fa-google-plus" /></a></span>
          <span class="icon"><a href="#"><i class="fa fa-pinterest" /></a></span>
        </div> <!-- End .share-iocn -->
      </div> <!-- End .bio -->
    </div> <!-- End .author-box -->
    <!--<div class="related-post">-->
    <!--  <span class="title">Realted Post</span>-->
    <!--  <div class="row">-->
    <!--    <div class="col-md-4">-->
    <!--      <div class="item">-->
    <!--        <a href="#">-->
    <!--          <img-->
    <!--            src="images/placeholder-post-thum.jpg"-->
    <!--            alt="Post"-->
    <!--          >-->
    <!--          <h4>Sophisticated Kiev Home Makes</h4>-->
    <!--        </a>-->
    <!--        <span>JUne 14, 2015</span>-->
    <!--      </div> &lt;!&ndash; End .item &ndash;&gt;-->
    <!--    </div> &lt;!&ndash; End .col-md-4 &ndash;&gt;-->
    <!--    <div class="col-md-4">-->
    <!--      <div class="item">-->
    <!--        <a href="#">-->
    <!--          <img-->
    <!--            src="images/placeholder-post-thum.jpg"-->
    <!--            alt="Post"-->
    <!--          >-->
    <!--          <h4>Sophisticated Kiev Home Makes</h4>-->
    <!--        </a>-->
    <!--        <span>June 14, 2015</span>-->
    <!--      </div> &lt;!&ndash; End .item &ndash;&gt;-->
    <!--    </div> &lt;!&ndash; End .col-md-4 &ndash;&gt;-->
    <!--    <div class="col-md-4">-->
    <!--      <div class="item">-->
    <!--        <a href="#">-->
    <!--          <img-->
    <!--            src="images/placeholder-post-thum.jpg"-->
    <!--            alt="Post"-->
    <!--          >-->
    <!--          <h4>Sophisticated Kiev Home Makes</h4>-->
    <!--        </a>-->
    <!--        <span>JUne 14, 2015</span>-->
    <!--      </div> &lt;!&ndash; End .item &ndash;&gt;-->
    <!--    </div> &lt;!&ndash; End .col-md-4 &ndash;&gt;-->
    <!--  </div> &lt;!&ndash; End .row &ndash;&gt;-->
    <!--</div> &lt;!&ndash; End .related-post &ndash;&gt;-->
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
        name
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
    }
  }
}
</script>
