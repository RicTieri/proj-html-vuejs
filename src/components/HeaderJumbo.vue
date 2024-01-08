<template>
  <div class="jumbo-container">
    <button>prev</button>
    <img src="../assets/img/h3-rev-img-6.png" alt="jumbo">
    <button>next</button>
  </div>
</template>
<script>
export default {
  
}
</script>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

.jumbo-container{
  @include flex(row,space-between,center);

  background-image: url(../assets/img/h3-rev-img-5.png);
  background-repeat: no-repeat;
  background-position: center;
  margin-bottom: 4rem;
}
</style>