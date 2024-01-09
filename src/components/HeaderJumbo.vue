<template>
  <div class="jumbo-container" :style="{ backgroundImage: 'url(' + getImageUrl(jumboSets[currentJumbo].background) + ')' }">
    <button @click="nextJumbo">prev</button>
    <img :src="getImageUrl(jumboSets[currentJumbo].src)" alt="jumbo">
    <button @click="prevJumbo" class="l-btn">next</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      jumboSets:[
        {
          src:'h3-rev-img-2.png',
          background: 'h3-rev-img-1.png'
        },
        {
          src:'h3-rev-img-4.png',
          background: 'h3-rev-img-3.png'
        },
        {
          src:'h3-rev-img-6.png',
          background: 'h3-rev-img-5.png'
        },
      ],
      currentJumbo: 0,
    }
  },
  methods: {
    getImageUrl: function(path) {
      return new URL(`../assets/img/${path}`, import.meta.url).href;
    },
    nextJumbo() {
      this.currentJumbo = (this.currentJumbo + 1) % this.jumboSets.length;
    },
    prevJumbo() {
      this.currentJumbo = (this.currentJumbo - 1 + this.jumboSets.length) % this.jumboSets.length;
    },
  },
}
</script>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

.jumbo-container{
  @include flex(row,space-between,center);

  background-repeat: no-repeat;
  background-position: center;
  margin-bottom: 4rem;

  img{
    height: 500px
  }

  button{
    @include btn-rounded-corner;
    writing-mode: vertical-rl;
    color: $fill-red;
    font-size: .6rem;
    &.l-btn{
      @include rotate
    }
  }
}
</style>