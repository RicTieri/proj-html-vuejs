<template>
  <div class="menu-heading">
    <span>choose your flavor</span>
    <h1>the best pizza menu in town</h1>
    <p>Lorem ipsum dolor Sit arnet. consectetur adipiscing Ut blandit arcu tn
      pretium molestie. Interdum et malesuada fames ac.</p>
  </div>
  <div class="wrapper">
    <PizzaCard v-for="pizza in menu" :pizza="pizza" />
    <a href="#" class="pizza-popup">
      <img src="../assets/svg/svg-4.svg" alt="pizza popup">
    </a>
    <div class="chart-popup">
      <a href="#" class="bg-load">
        <img src="../assets/svg/svg-7.svg" alt="load">
      </a>
      <a href="#">
        <img src="../assets/svg/svg-9.svg" alt="chart">
      </a>
    </div>
  </div>
</template>
<script>
import PizzaCard from './PizzaCard.vue';

export default {
  data() {
    return {
      menu: [
        {
          src: 'h3-product-img-1a-100x100.png',
          name: 'bismark',
          price: '$15.00',
          sold: false
        },
        {
          src: 'h3-product-img-2a-150x150.png',
          name: 'fiori di zucca',
          price: '$5.00 - $50.00',
          sold: false
        },
        {
          src: 'h3-product-img-3a-150x150.png',
          name: 'valdostana',
          price: '$45.00',
          sold: true
        },
        {
          src: 'h3-product-img-4a-150x150.png',
          name: 'pizza tartufata',
          price: '$15.00',
          sold: false
        },
        {
          src: 'h3-product-img-5a-150x150.png',
          name: 'francescana',
          price: '$25.00',
          sold: false
        },
        {
          src: 'h3-product-img-6a-100x100.png',
          name: 'campagnola',
          price: '$95.00',
          sold: false
        },
      ]
    }
  },
  components: {
    PizzaCard
  }
}
</script>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

.menu-heading {
  width: 25%;
  margin: 0 auto;
  text-align: center;
  padding: 6rem 0;

  span {
    display: inline-block;
    text-transform: uppercase;
    color: $fill-red;
    font-weight: 600;
    margin-bottom: 1rem;
  }

  h1 {
    text-transform: uppercase;
    font-size: 2.5rem;
    margin-bottom: 1rem;
  }

  p {
    line-height: 1.8rem;
    font-size: 1.1rem;
    color: $text-grey;
  }
}

.wrapper {
  @include flex(row, space-evenly, center);
  padding-bottom: 12rem;
  position: relative;

  .chart-popup{
    position: absolute;
    right: 0;
    bottom: -40px;
    width: 40px;
    z-index: 1;
    
    a{
      display: inline-block;
      padding: .7rem;
      width: 40px;
      height: 40px;
      background-color: white;
      
      &.bg-load{
        background-color: $fill-load;
        margin-bottom: .5rem;
      }

      img{
        width: 100%
      }
    }
  }

}

a.pizza-popup {
  @include flex(row, center, center);
  @include pop-up-pizza(35rem, 2rem);
  background-color: $bg-light;
}
</style>