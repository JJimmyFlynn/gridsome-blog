<template>
  <widget heading="Categories">
    <ul class="category-list">
      <li
        v-for="{ node: category } in $static.context.edges"
        :key="category.slug"
        class="cat-item"
      >
        <a href="#">{{ category.title }} <span>({{ category.belongsTo.totalCount }})</span></a>
      </li>
    </ul> <!-- End .category-list -->
  </widget>
</template>

<static-query>
  query {
    context: allContentfulCategories {
      edges {
        node {
          title,
          slug,
          belongsTo {
            totalCount
          }
        }
      }
    }
  }
</static-query>

<script>
import Widget from '../Widget.vue'

export default {
  name: 'Categories',
  components: { Widget }
}
</script>
