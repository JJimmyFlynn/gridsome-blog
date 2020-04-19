<template>
  <div class="widget-box">
    <div
      v-if="heading"
      class="widget-title"
    >
      <span>{{ heading }}</span>
      <div class="line" />
    </div> <!-- End .widget-title -->
    <div class="widget-item">
      <slot />
    </div> <!-- End .widget-item -->
  </div> <!-- End .widget-box -->
</template>

<script>
export default {
  name: 'Widget',
  props: {
    heading: {
      type: String,
      default: ''
    }
  }
}
</script>
