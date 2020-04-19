<template>
  <Layout>
    <section id="slider">
      <div class="style-two">
        <div class="bg-style-two">
          <div class="container">
            <div class="row">
              <div class="col-md-10 col-md-offset-1">
                <!--<g-image src="~/assets/images/author.jpg" alt=""></g-image>-->
                <h1>{{ $page.context.heroHeading }}</h1>
                <h2>{{ $page.context.heroSubHeading }}</h2>
                <p>{{ $page.context.heroBlurb }}</p>
              </div>
            </div>
          </div>
        </div>
      </div> <!-- End .style-two -->
    </section>
    <!--
        =====================
          End Section Slider
        =====================
     -->
    <section id="content">
      <div class="container">
        <div class="row">
          <div class="col-md-8">
            <div class="primary">
                <post-teaser
                  v-for="post in $page.posts.edges"
                  :key="post.key"
                  :post="post.node"
                ></post-teaser>
            </div>
            <!--
                ===============
                  End .primary
                ===============
            -->
          </div> <!-- End .col-md-8 -->
          <div class="col-md-4">
            <div class="sidebar">
              <div class="widget-box">
                <div class="widget-title">
                  <span>About Me</span>
                  <div class="line"></div>
                </div> <!-- End .widget-title -->
                <div class="widget-item">
                  <img src="/assets/images/about-me.jpg" alt="About Me Image">
                  <div class="sidebar-text">
                    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut
                       labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud.</p>
                  </div> <!-- End .sidebar-text -->
                </div> <!-- End .widget-item -->
              </div> <!-- End .widget-box -->

              <div class="widget-box">
                <div class="widget-title">
                  <span>SUBSCRIBE & FOLLOW</span>
                  <div class="line"></div>
                </div> <!-- End .widget-title -->
                <div class="widget-item">
                  <span class="social"><a href="#"><i class="fa fa-facebook"></i></a></span>
                  <span class="social"><a href="#"><i class="fa fa-twitter"></i></a></span>
                  <span class="social"><a href="#"><i class="fa fa-google-plus"></i></a></span>
                  <span class="social"><a href="#"><i class="fa fa-pinterest"></i></a></span>
                  <span class="social"><a href="#"><i class="fa fa-instagram"></i></a></span>
                  <span class="social"><a href="#"><i class="fa fa-youtube-play"></i></a></span>
                  <span class="social"><a href="#"><i class="fa fa-rss"></i></a></span>
                </div> <!-- End .widget-item -->
              </div> <!-- End .widget-box -->

              <div class="widget-box">
                <div class="widget-title">
                  <span>Recent Post</span>
                  <div class="line"></div>
                </div> <!-- End .widget-title -->
                <div class="widget-item">
                  <ul class="sidebar-post">
                    <li class="item">
                      <div class="thum-img">
                        <img src="/assets/images/placeholder-post-thum.jpg" alt="Small Thumbnail Image">
                      </div> <!-- End .thum-img -->
                      <div class="post-meta">
                        <h4><a href="#">Sophisticated Kiev Home Makes Kiev Home Makes</a></h4>
                        <p>June 14, 2015</p>
                      </div> <!-- End .post-meta -->
                    </li> <!-- End .item -->

                    <li class="item">
                      <div class="thum-img">
                        <img src="/assets/images/placeholder-post-thum.jpg" alt="Small Thumbnail Image">
                      </div> <!-- End .thum-img -->
                      <div class="post-meta">
                        <h4><a href="#">Sophisticated Kiev Home Makes</a></h4>
                        <p>June 14, 2015</p>
                      </div> <!-- End .post-meta -->
                    </li> <!-- End .item -->

                    <li class="item">
                      <div class="thum-img">
                        <img src="/assets/images/placeholder-post-thum.jpg" alt="Small Thumbnail Image">
                      </div> <!-- End .thum-img -->
                      <div class="post-meta">
                        <h4><a href="#">Sophisticated Kiev Home Makes</a></h4>
                        <p>June 14, 2015</p>
                      </div> <!-- End .post-meta -->
                    </li> <!-- End .item -->

                    <li class="item">
                      <div class="thum-img">
                        <img src="/assets/images/placeholder-post-thum.jpg" alt="Small Thumbnail Image">
                      </div> <!-- End .thum-img -->
                      <div class="post-meta">
                        <h4><a href="#">Sophisticated Kiev Home Makes</a></h4>
                        <p>June 14, 2015</p>
                      </div> <!-- End .post-meta -->
                    </li> <!-- End .item -->

                    <li class="item">
                      <div class="thum-img">
                        <img src="/assets/images/placeholder-post-thum.jpg" alt="Small Thumbnail Image">
                      </div> <!-- End .thum-img -->
                      <div class="post-meta">
                        <h4><a href="#">Sophisticated Kiev Home Makes</a></h4>
                        <p>June 14, 2015</p>
                      </div> <!-- End .post-meta -->
                    </li> <!-- End .item -->
                  </ul> <!-- End .sidebar-post -->
                </div> <!-- End .widget-item -->
              </div> <!-- End .widget-box -->

              <div class="widget-box">
                <div class="widget-title">
                  <span>Category</span>
                  <div class="line"></div>
                </div> <!-- End .widget-title -->
                <div class="widget-item">
                  <ul class="category-list">
                    <li class="cat-item"><a href="#">Lifestyle <span>(5)</span></a></li>
                    <li class="cat-item"><a href="#">Music<span>(15)</span></a></li>
                    <li class="cat-item"><a href="#">Travel<span>(8)</span></a></li>
                    <li class="cat-item"><a href="#">Video<span>(11)</span></a></li>
                    <li class="cat-item"><a href="#">Audio<span>(10)</span></a></li>
                  </ul> <!-- End .category-list -->
                </div> <!-- End .widget-item -->
              </div> <!-- End .widget-box -->

            </div>
            <!--
               =================
                 End .sidebar
               =================
            -->
          </div> <!-- End .col-md-4 -->
        </div> <!-- End .row -->
      </div> <!-- End .container -->
    </section>
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
          body,
          heroImage {
            file {
              url,
            }
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
