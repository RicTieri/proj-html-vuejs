<template>
  <div class="container">
    <div class="showcase" v-for="element in showcase">
      <img :src="getImageUrl(element.src)" alt="don peppe">
    </div>
  </div>
  <div class="container testimonials">
    <button>prev</button>
    <div>

    </div>
    <button class="l-btn">next</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      showcase:[
        {
          src: 'h3-img-1.jpg',
          link: '#'
        },
        {
          src: 'h3-img-2.jpg',
          link: '#'
        },
        {
          src: 'h3-img-3.jpg',
          link: '#'
        },
        {
          src: 'h3-img-4.jpg',
          link: '#'
        },
      ],
      testimonials:[
        {
          content:'"FORGET THE TRENDY PIZZA SHOPS, THIS HIDDEN SPOT MAKES THE BEST NEW YORK-STYLE PIZZA SLICE IN NAPLES"',
          credit:'washinton post 2018'
        },
        {
          content:'"FORGET THE TRENDY PIZZA SHOPS, THIS HIDDEN SPOT MAKES THE BEST NEW YORK-STYLE PIZZA SLICE IN NAPLES"',
          credit:'washinton post 2018'
        },
        {
          content:'"FORGET THE TRENDY PIZZA SHOPS, THIS HIDDEN SPOT MAKES THE BEST NEW YORK-STYLE PIZZA SLICE IN NAPLES"',
          credit:'washinton post 2018'
        },
      ]
    }
  },
  methods: {
    getImageUrl: function(path) {
      return new URL(`../assets/img/${path}`, import.meta.url).href;
    }
  },
}
</script>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

.container{
  @include flex(row, space-between, center);
  gap: .5rem;
  margin-bottom: .5rem;

}
.testimonials{
   background-image: url(../assets/img/h3-testimonials-bckgrnd.jpg);
}
.showcase{
  width: calc(100% / 4);

  & img{
    display: block;
    width: 100%;
  }
}

button{
    @include btn-rounded-corner;
    writing-mode: vertical-rl;
    color: $fill-red;
    border: none;
    font-size: .6rem;
    &.l-btn{
      @include rotate
    }
  }
  
</style>