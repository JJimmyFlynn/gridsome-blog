<template>
  <div v-html="richtextToHTML(richtext)" />
</template>

<script>
import Contentful from '../mixins/Contentful.vue'

export default {
  name: 'Richtext',
  mixins: [Contentful],
  props: {
    richtext: {
      type: Object,
      required: true
    }
  }
}
</script>
