<template>
  <time>{{ humanReadableDate(new Date(dateString), 'LLLL Lo, yyyy') }}</time>
</template>

<script>
import Dates from '../mixins/Dates.vue'

export default {
  name: 'PostDate',
  mixins: [Dates],
  props: {
    dateString: {
      type: String,
      required: true
    }
  }
}
</script>
