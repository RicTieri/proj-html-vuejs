<template>
  <div class="container">
    <div class="custom-bg">
      <img src="../assets/img/h1-img-7n.png" alt="pizza special">
    </div>
    <div class="advertise">
      <div class="wrapper">
        <h1>Specials*</h1>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent ut.</p>
        <div class="details" v-for="special in specials">
          <h3>{{ special.price }}</h3>
          <div>
            <h3>{{ special.title }}</h3>
            <p>{{ special.description }}</p>
          </div>
        </div>
      </div>
    </div>
    <a href="#" class="pizza-popup">
      <img src="../assets/svg/svg-4.svg" alt="pizza popup">
    </a>
  </div>
</template>
<script>
export default {
  data() {
    return {
      specials: [
        {
          price: '$10',
          title: 'combo piccolo',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent ut aliquam dui.'
        },
        {
          price: '$20',
          title: 'combo mezzo',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent ut aliquam dui.'
        },
        {
          price: '$30',
          title: 'combo grande',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent ut aliquam dui.'
        },
      ]
    }
  },
}
</script>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

.container {
  @include flex(row, center, flex-start);
  position: relative;
  margin-bottom: .5rem;
  
  &>* {
    width: 50%;
  }
  
  .custom-bg {
    @include flex(row, center, center);
    padding: 12rem;
    height: 800px;
    background-image: url(../assets/img/h1-img-4.jpg);
    background-position: center;
  }

  h1 {
    text-transform: uppercase;
    margin-bottom: .75rem;
    font-size: 2.5rem;
  }

  p {
    margin-bottom: 2rem;
    font-size: 1.2rem;
    color: $text-grey;
  }

}

.advertise {
  padding: 10rem 15rem 0;

  .wrapper{
    width: 80%
  }
}

.details {
  @include flex(row, flex-start, flex-start);

  h3 {
    text-transform: uppercase;
    margin-bottom: .5rem;
    font-size: 1.5rem;
  }


  &>h3 {
    color: $fill-red;
    margin-right: 1rem;
  }

  p{
    font-size: 1rem;
    line-height: 1.5rem
  }
}

a.pizza-popup {
  @include flex(row, center, center);
  @include pop-up-pizza(16rem, 2rem);
  background-color: $bg-light;
}
</style>