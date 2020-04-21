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

    <recent-posts />

    <categories/>
  </div>
</template>
<script>
import Widget from '../Widget.vue'
import RecentPosts from './RecentPosts.vue'
import AboutMe from './AboutMe.vue'
import Categories from './Categories.vue';

export default {
  name: 'Sidebar',
  components: {Categories, AboutMe, RecentPosts, Widget }
}
</script>
