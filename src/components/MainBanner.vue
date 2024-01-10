<template>
  <div class="container">
    <div class="showcase" v-for="element in showcase">
      <img :src="getImageUrl(element.src)" alt="don peppe">
      <div class="view">
        <a href="#">
          <img src="../assets/img/iconmonstr-eye-lined-240.png" alt="view">
        </a>
      </div>
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
    <a href="#" class="pizza-popup">
      <img src="../assets/svg/svg-4.svg" alt="pizza popup">
    </a>
  </div>
</template>
<script>
export default {
  data() {
    return {
      showcase: [
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
      testimonials: [
        {
          content: '"FORGET THE TRENDY PIZZA SHOPS, THIS HIDDEN SPOT MAKES THE BEST NEW YORK-STYLE PIZZA SLICE IN NAPLES"',
          credit: 'washington post 2018'
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
    getImageUrl: function (path) {
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

.container {
  @include flex(row, space-between, center);
  gap: .5rem;
  margin-bottom: .5rem;

}

.showcase {
  width: calc(100% / 4);
  position: relative;

  & img {
    display: block;
    width: 100%;
  }

  &:hover .view {
    @include flex(row, center, center);
  }

  .view {
    display: none;
    background-image: url(../assets/img/dotted-bgd.png);
    background-size: cover;
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;

    a {
      height: 60px;
      border-radius: 50%;
      padding: 1rem;
      background-color: $fill-red;

      img {
        height: 100%;
      }
    }
  }

}

.testimonials {
  background-image: url(../assets/img/h3-testimonials-bckgrnd.jpg);
  background-position: center;
  background-size: cover;
  margin-bottom: .5rem;
  min-height: 400px;
  position: relative;
  text-align: center;
  text-transform: uppercase;

  div.testimonials-wrapper {
    padding: 4rem 0;
    width: 35%;
    font-weight: bold;
  }

  p {
    font-size: 1.8rem;
    line-height: 2.7rem;

    &.quotation-marks {
      margin-bottom: 1rem;
      height: 70px;
      @include rotate;

      img {
        height: 100%;
      }
    }

    &.text-red {
      margin-bottom: 1rem;
      color: $fill-red;
      font-size: 1rem;
      font-weight: 600;
    }
  }

  span {
    display: inline-block;
    height: 8px;
    margin: .25rem;
    filter: opacity(0.2);

    img {
      height: 100%
    }

    &.active {
      filter: opacity(1)
    }

  }

  button {
    @include btn-rounded-corner;
    writing-mode: vertical-rl;
    background-color: white;
    color: $fill-red;
    border: none;
    font-size: .6rem;

    &.l-btn {
      @include rotate
    }
  }

  a.pizza-popup {
    @include flex(row, center, center);
    @include pop-up-pizza(2rem, 2rem)
  }
}</style>