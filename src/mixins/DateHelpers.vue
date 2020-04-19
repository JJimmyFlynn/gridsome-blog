<script>
import { format } from 'date-fns'

export default {
  name: 'DateHelpers',
  methods: {
    humanReadableDate (date, formatString) {
      return format(date, formatString)
    }
  }
}
</script>

<style scoped>

</style>
