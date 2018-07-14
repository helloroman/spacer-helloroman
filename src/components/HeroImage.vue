<template>
  <div class="heroImage" />
</template>
<script>
export default {
  name: 'HeroImage',
};
</script>
<style lang="scss" scoped>
  .heroImage {
    position: fixed;
    top: 0;
    z-index: -1;
    width: 100%;
    height: 100vh;
    background-image: url('../assets/heroimage.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: 80% 0%;
  }

  .heroImage::after {
    content: '';
    background: rgba(0,0,0, .2);
    position: absolute;
    top: 0;
    left: 0;
    z-index: 1;
    width: 100%;
    height: 100vh;
  }
</style>
