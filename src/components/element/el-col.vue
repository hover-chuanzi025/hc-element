<template>
  <div :class="['el-col', `el-col-${span}`]" :style="style">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'el-col',
  props: {
    span: {
      default: 24,
      type: Number,
    },
  },
  computed: {
    gutter() {
      let parent = this.$parent;
      while (parent && parent.$options.name !== 'ElRow') {
        parent = parent.$parent;
      }
      return parent ? parent.gutter : 0;
    },
    style() {
      const style = {};
      if (this.gutter) {
        style.paddingLeft = `${this.gutter / 2}px`;
        style.paddingRight = style.paddingLeft;
        console.log(style);
        return style;
      }
      return {};
    },
  },
};
</script>
