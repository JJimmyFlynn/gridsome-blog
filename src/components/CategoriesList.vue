<template>
  <span>
    <g-link
      v-for="(category, index) in categories"
      :key="category.id"
      :to="`/blog/category/${category.slug}`"
    >
      {{ category.title }}<template v-if="index < categories.length - 1">,
      </template>
    </g-link>
  </span>
</template>

<script>
export default {
  name: 'CategoriesList',
  props: {
    categories: {
      type: Array,
      required: true
    }
  }
}
</script>
