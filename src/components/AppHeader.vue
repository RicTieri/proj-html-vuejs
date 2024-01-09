<template>
  <header>
    <nav>
      <a href="#" class="bg-red">order online</a>
      <ul>
        <li>
          <a href="#">
            <img src="../assets/svg/svg-0.svg" alt="home">
            home
          </a>
        </li>
        <li><a href="#">pages</a></li>
        <li><a href="#">menu</a></li>
        <li>
          <img src="../assets/img/h5-logo-divided-header.png" alt="logo">
        </li>
        <li><a href="#">event</a></li>
        <li><a href="#">blog</a></li>
        <li><a href="#">landing</a></li>
      </ul>
      <div>
        <a href="#">
          <img src="../assets/svg/svg-1.svg" alt="cart">
          cart
        </a>
        <a href="#">
          <img src="../assets/img/iconmonstr-magnifier-4-240.png" alt="magnifier" class="reverse">
          search</a>
      </div>
    </nav>
    <HeaderJumbo />
  </header>
</template>
<script>
import HeaderJumbo from './HeaderJumbo.vue';
export default {
  components: {
    HeaderJumbo
  }
}
</script>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

header {
  background-image: url(../assets/img/cielostellato.PNG);
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  padding: 2rem 0;
  margin-bottom: .5rem
}

nav {
  @include flex(row, space-between, center);
  padding: 2rem 0;
  width: 60%;
  margin: 0 auto;
  text-transform: uppercase;
  color: white;

  a {
    @include flex(row, space-between, center);
    text-decoration: none;
    color: white;

    padding: .5rem .75rem;

    &.bg-red {
      background-color: $fill-red;
      padding: .5rem 1rem;
    }

    >img {
      width: 35px;
      padding: .25rem;
      filter: invert(1);

      &.reverse{
        scale: 0.7;
        transform: scaleX(-1)
      }
    }
  }

  ul {
    @include flex(row, space-around, center);
    list-style: none;

    li {
      >img {
        height: 100px;
      }
    }
  }

  div {
    @include flex(row, space-between, center)
  }

}
</style>