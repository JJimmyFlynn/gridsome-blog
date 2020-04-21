<template>
  <div class="sidebar">
    <about-me />

    <recent-posts />

    <categories />
  </div>
</template>
<script>
import Widget from '../Widget.vue'
import RecentPosts from './RecentPosts.vue'
import AboutMe from './AboutMe.vue'
import Categories from './Categories.vue'

export default {
  name: 'Sidebar',
  components: { Categories, AboutMe, RecentPosts, Widget }
}
</script>
