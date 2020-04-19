<template>
  <widget heading="About Me">
    <g-image
      :src="getAboutImage()"
      alt="About Me Image"
    />
    <div class="sidebar-text">
      <p>
        {{ $static.context.aboutMeCopy }}
      </p>
    </div> <!-- End .sidebar-text -->
  </widget>
</template>

<static-query>  query {
  context: contentfulSettingsSidebar( id: "6DTtu2fgL8MFRD5iaxCu7i") {
    aboutMeCopy,
    aboutMeImage {
      file {
        url
      }
    }
  }
}
</static-query>

<script>
import Widget from '../Widget.vue'
import Contentful from '../../mixins/Contentful.vue'

export default {
  name: 'AboutMe',
  components: { Widget },
  mixins: [Contentful],
  methods: {
    getAboutImage() {
      return this.manipulateImage(this.$static.context.aboutMeImage.file.url, '?w=350')
    }
  }
}
</script>
