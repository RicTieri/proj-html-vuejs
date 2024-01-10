<template>
  <footer>
    <div class="wrapper"></div>
    <div class="wrapper">
      <img src="../assets/img/footer-img-1.jpg" alt="footer img">
    </div>
  </footer>
</template>
<script>
export default {
  data() {
    return {
      location:[
        {
          route:'',
          city
        }
      ]
    }
  },
}
</script>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

footer{
  @include flex(row,flex-start, stretch);

  .wrapper{
    background-image: url(../assets/img/cielostellato.PNG);
    width: 50%;
  }
}
</style>