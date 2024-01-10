<template>
  <div class="menu-container">
    <div class="img-wrapper">
      <img :src="getImageUrl(pizza.src)" :alt="pizza.name">
      <span v-if="pizza.sold">sold</span>
    </div>
    <p>
      {{ pizza.name }}
    </p>
    <span>
      {{ pizza.price }}
    </span>
  </div>
</template>

<script>
export default {
  props:{
    pizza:{
      type: Object,
      required: true
    }
  },
  methods: {
    getImageUrl: function (path) {
      return new URL(`../assets/img/${path}`, import.meta.url).href;
    },
  }
}
</script>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

.menu-container{
  width: 13%;
  text-align: center;
  font-size: 1.3rem;
  
  .img-wrapper{
    position: relative;
    width: 100%;
    border-radius: 50%;
    
    img{
      width: 100%;
      margin-bottom: 1rem;
    }

    span{
      @include flex(row,center,center);
      position: absolute;
      top: .4rem;
      right: .4rem;
      display: inline-block;
      text-align: center;
      text-transform: uppercase;
      background-color: $fill-red;
      color: white;
      font-size: .8rem;
      border-radius: 50%;
      width: 60px;
      line-height: 60px
    }
  }

  
  p{
    color: $fill-gold;
    text-transform: uppercase;
    font-weight: 600;
    margin-bottom: .5rem;
  }

  >span{
    color: $fill-red;
    font-weight: 600;
  }
}
  
</style>