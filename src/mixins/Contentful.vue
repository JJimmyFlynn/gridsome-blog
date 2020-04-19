<script>
export default {
  name: 'Contentful',
  methods: {
    manipulateImage (imageUrl, manipulationsString) {
      return `${imageUrl}?${manipulationsString}`
    }
  }
}
</script>
