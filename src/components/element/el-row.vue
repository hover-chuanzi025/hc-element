<template>
  <div class="el-row">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'ElRow',
  props: {
    gutter: {
      default: 0,
      type: Number,
    },
  },
  computed: {
  },
};
</script>
