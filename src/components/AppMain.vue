<template>
  <main>
    <MainBanner/>
    <MainSpecials/>
    <MainAdvertise/>
    <MainPartner/>
    <MainMenu/>
  </main>
</template>
<script>
import MainBanner from './MainBanner.vue';
import MainSpecials from './MainSpecials.vue';
import MainAdvertise from './MainAdvertise.vue';
import MainPartner from './MainPartner.vue';
import MainMenu from './MainMenu.vue';

export default {
  components:{
    MainBanner,
    MainSpecials,
    MainAdvertise,
    MainPartner,
    MainMenu
  }
  
}
</script>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;
  
</style>