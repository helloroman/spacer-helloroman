<template>
  <div class="searchWrapper">
    <input
      id="search"
      name="search"
      v-model="searchValue"
      @input="handleInput"
    />
  </div>
</template>
<script>
export default {
  name: 'SearchInput',
};
</script>
<style lang="scss" scoped>
  .searchWrapper {
    margin-top: 50px;
    display: flex;
    flex-direction: column;
    width: 250px;

    input {
      color: white;
      text-align: center;
      font-size: 18px;
      font-weight: 300;
      height: 30px;
      border: 0;
      background: none;
      border-bottom: 1px solid white;
      transition: box-shadow .3s ease-out;

      @media (min-width: 1024px) {
        font-weight: 400;
      }
    }

    input:focus {
      outline: none;
      box-shadow: 0 10px 20px -8px rgba(255,255,255, .5);
    }
  }
</style>
