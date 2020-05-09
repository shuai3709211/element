<template>
  <svg v-if="isElIcon"
          class="icon"
          :style="{ fontSize: size + 'px', color: color }"
          aria-hidden="true"
  >
    <use :xlink:href="'#' + name"></use>
  </svg>
  <i v-else :class="'el-icon-' + name"></i>
</template>

<script>
  export default {
    name: 'ElIcon',

    props: {
      name: String,
      size: {
        type: [Number, String],
        default: 14
      },
      color: {
        type: String,
        default: null
      }
    },
    computed: {
      isElIcon() {
        if (!this.name) return true;
        return this.name.indexOf('el-icon') !== -1;
      }
    }
  };
</script>
<style scoped>
  .icon {
    width: 1em;
    height: 1em;
    vertical-align: -0.15em;
    fill: currentColor;
    overflow: hidden;
  }
</style>
