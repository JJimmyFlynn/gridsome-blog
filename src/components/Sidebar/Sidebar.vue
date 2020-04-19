<template>
  <div class="sidebar">
    <AboutMe />

    <widget heading="Subscribe &amp; Follow">
      <span class="social"><a href="#"><i class="fa fa-facebook" /></a></span>
      <span class="social"><a href="#"><i class="fa fa-twitter" /></a></span>
      <span class="social"><a href="#"><i class="fa fa-google-plus" /></a></span>
      <span class="social"><a href="#"><i class="fa fa-pinterest" /></a></span>
      <span class="social"><a href="#"><i class="fa fa-instagram" /></a></span>
      <span class="social"><a href="#"><i class="fa fa-youtube-play" /></a></span>
      <span class="social"><a href="#"><i class="fa fa-rss" /></a></span>
    </widget>

    <recent-posts></recent-posts>

    <widget heading="Categories">
      <ul class="category-list">
        <li class="cat-item">
          <a href="#">Lifestyle <span>(5)</span></a>
        </li>
        <li class="cat-item">
          <a href="#">Music<span>(15)</span></a>
        </li>
        <li class="cat-item">
          <a href="#">Travel<span>(8)</span></a>
        </li>
        <li class="cat-item">
          <a href="#">Video<span>(11)</span></a>
        </li>
        <li class="cat-item">
          <a href="#">Audio<span>(10)</span></a>
        </li>
      </ul> <!-- End .category-list -->
    </widget>
  </div>
</template>
<script>
import Widget from '../Widget.vue'
import RecentPosts from './RecentPosts.vue';
import AboutMe from './AboutMe.vue';

export default {
  name: 'Sidebar',
  components: {AboutMe, RecentPosts, Widget }
}
</script>
