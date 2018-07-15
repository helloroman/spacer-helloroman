<template>
  <div class="outerWrapper">
    <div class="innerWrapper">
      <div class="photo">
        <img :src="photo">
      </div>
      <div class="description">
        <h2 class="title">{{ title }}</h2>
        <p class="description">
          {{ description }}
        </p>
      </div>
    </div>
    <div class="close" @click="$emit('closeModal')" />
  </div>
</template>
<script>
export default {
  name: 'Modal',
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      photo: null,
      title: null,
      description: null,
    };
  },
  mounted() {
    this.photo = this.item.links[0].href;
    this.title = this.item.data[0].title;
    this.description = this.item.data[0].description.substring(0, 200);
  },
};
</script>
<style lang="scss" scoped>
  .outerWrapper {
    background: #f6f6f6;
    max-width: 100%;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;

    @media (min-width: 1024px) {
      max-width: 70%;
      height: 60%;
      left: 0;
      right: 0;
      top: 0;
      bottom: 0;
      margin: auto;
      box-shadow: 0 30px 30px -10px rgba(0,0,0, .3);
    }
  }

  .close {
    position: absolute;
    width: 30px;
    height: 30px;
    padding: 30px;
    right: 0;
    top: 0;
    cursor: pointer;

    &::before,
    &::after {
      position: absolute;
      top: 30px;
      right: 20px;
      content: '';
      width: 20px;
      height: 2px;
      background: black;
      display: block;
    }

    &::before {
      transform: rotate(45deg);
    }

    &::after {
      transform: rotate(-45deg);
    }
  }

  .innerWrapper {
    display: flex;
    height: 100%;
    padding: 50px;
    justify-content: center;
    align-items: center;
    flex-direction: column;

    @media (min-width: 1024px) {
      flex-direction: row;

      .photo {
        min-width: 50%;
        margin-right: 20px;
      }
    }

    .photo {
      width: 100%;
      height: auto;
      background: black;

      img {
        width: 100%;
      }
    }

    .description {
      color: #333;
    }

    .title {
       color: #1e3d4a;
    }
  }
</style>
