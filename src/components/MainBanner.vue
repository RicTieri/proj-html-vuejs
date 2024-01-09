<template>
  <div class="container">
    <div class="showcase" v-for="element in showcase">
      <img :src="getImageUrl(element.src)" alt="don peppe">
    </div>
  </div>
  <div class="container testimonials">
    <button @click="prevTestimonial">prev</button>
    <div class="testimonials-wrapper">
      <p class="quotation-marks">
        <img src="../assets/img/iconmonstr-quote-3-240.png" alt="quotation marks">
      </p>
      <p>{{ testimonials[currentTestimonial].content }}</p>
      <p class="text-red">{{ testimonials[currentTestimonial].credit }}</p>
      <span v-for="(element, index) in testimonials" :class="(index == currentTestimonial) ? 'active' : ''">
        <img src="../assets/img/iconmonstr-shape-19-240.png" alt="dot">
      </span>
    </div>
    <button @click="nextTestimonial" class="l-btn">next</button>
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
          content: '"AN AMAZING PIZZA EXPERIENCE, THE TASTE IS UNMATCHED"',
          credit: 'Foodie Magazine'
        },
        {
          content: '"DON PEPPE\'S PIZZA IS SIMPLY PHENOMENAL, A MUST-TRY!"',
          credit: 'Pizza Enthusiast Blog'
        },
      ],
      currentTestimonial: 0,
    }
  },
  methods: {
    getImageUrl: function(path) {
      return new URL(`../assets/img/${path}`, import.meta.url).href;
    },
    nextTestimonial() {
      this.currentTestimonial = (this.currentTestimonial + 1) % this.testimonials.length;
    },
    prevTestimonial() {
      this.currentTestimonial = (this.currentTestimonial - 1 + this.testimonials.length) % this.testimonials.length;
    },
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
.showcase{
  width: calc(100% / 4);
  
  & img{
    display: block;
    width: 100%;
  }
}
.testimonials{
   background-image: url(../assets/img/h3-testimonials-bckgrnd.jpg);
   background-position: center;
   min-height: 400px;
   text-align: center;
   text-transform: uppercase;
  
  div.testimonials-wrapper{
    padding: 4rem 0;
    width: 30%;
    font-weight: bold;
  }

   p{
    margin-bottom: 1rem;
     &.quotation-marks{
      height: 70px;
      transform: rotate(180deg);

      img{
        height: 100%;
      }
     }

     &.text-red{
      color: $fill-red
     }
   }
   
   span{
    display: inline-block;
    height: 10px;
    margin: .25rem;
    filter: opacity(0.2);
    
    img{
     height: 100%
    }
     &.active{
      filter: opacity(1)
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
}

  
</style>