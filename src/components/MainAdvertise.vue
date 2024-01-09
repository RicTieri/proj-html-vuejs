<template>
  <div class="wrapper">
    <div class="w-10 h-20 bg-r-1"></div>
    <div class="w-80 h-20 bg-c-1"></div>
    <div class="w-10 h-20 bg-l-1"></div>
    <div class="w-10 h-60 bg-r-2"></div>
    <div class="w-80 h-60 bg-c-2"></div>
    <div class="w-10 h-60 bg-l-2"></div>
    <div class="w-10 h-20 bg-r-3"></div>
    <div class="w-80 h-20 bg-c-3"></div>
    <div class="w-10 h-20 bg-l-3"></div>
    <p>go ahead and <br>build your <br> own pizza <br> we won't <br> judge!</p>
    <a href="#" class="pizza-popup">
      <img src="../assets/svg/svg-4.svg" alt="pizza popup">
    </a>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

.wrapper {
  @include flex(row, space-between, stretch);
  position: relative;
  flex-grow: 1;
  flex-wrap: wrap;
  height: 600px;
  width: 100%;
  margin-bottom: .5rem;

  & div {
    background-image: url(../assets/img/h3-background-img.jpg);
    background-repeat: no-repeat;

    &.w-10 {
      width: 8%;
    }

    &.w-80 {
      width: 84%;
    }

    &.h-20 {
      height: 25%;
    }

    &.h-60 {
      height: 50%;
    }

    &.bg-r-1 {
      background-position: bottom;
      background-position-x: right;
    }

    &.bg-r-2 {
      background-position: top;
      background-position-x: right;
    }

    &.bg-r-3 {
      background-position: center;
      background-position-x: right;
    }

    &.bg-c-1 {
      background-position: center;
      background-position-y: bottom;
    }

    &.bg-c-2 {
      background-position: center;
      background-position-y: top;
    }

    &.bg-c-3 {
      background-position: center;
      background-position-y: center;
    }

    &.bg-l-1 {
      background-position: left;
      background-position-y: top;
    }

    &.bg-l-2 {
      background-position: left;
      background-position-y: center;
    }

    &.bg-l-3 {
      background-position: left;
      background-position-y: bottom;
    }

  }

  p{
    position: absolute;
    text-transform: uppercase;
    color: white;
    font-size: 3.5rem;
    font-weight: 600;
    width: 20%;
    top: 20%;
    left: 22%
  }

  a.pizza-popup {
    @include flex(row, center, center);
    @include pop-up-pizza(11rem, 2rem);
    background-color: $bg-light;
  }
}</style>