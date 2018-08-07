<template>
  <div class="loader">
    <div class="loader-container" v-if="loading" :style="style">
      <img
        :src="Loader"
        height="32px"
        width="32px"
      />
    </div>
    <slot v-else></slot>
  </div>
</template>

<script>
import Loader from '@/assets/images/loader-green.svg';

export default {
  data() {
    return {
      Loader,
      style: {},
    };
  },
  props: {
    loading: {
      default: true,
      type: Boolean,
    },
    fullPage: {
      default: false,
      type: Boolean,
    },
  },
  created() {
    if (this.fullPage) {
      this.style = {
        position: 'fixed',
        zIndex: '1',
        top: '0',
        bottom: '0',
        left: '0',
        right: '0',
      };
    }
  },
};
</script>
<style lang="scss" scoped>
.loader-container {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
