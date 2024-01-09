<template>
  <main>
    <MainBanner/>
  </main>
</template>
<script>
import MainBanner from './MainBanner.vue';

export default {
  components:{
    MainBanner
  }
  
}
</script>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;
  
</style>