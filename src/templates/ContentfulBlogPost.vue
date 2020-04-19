<template>
    <Layout>
    </Layout>
</template>

<page-query>
  query Post ($path: String!) {
    context: contentfulBlogPost ( path: $path ) {
      title
    }
  }
</page-query>

<script>
export default {
  name: 'ContentfullBlogPost'
}
</script>
