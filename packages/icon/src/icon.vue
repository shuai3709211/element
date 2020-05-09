<template>
  <svg v-if="!isElIcon"
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

