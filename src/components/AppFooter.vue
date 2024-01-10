<template>
  <footer>
    <div class="wrapper link-wrap">
      <div class="column">
        <h3>find our restaurant</h3>
        <div v-for="location in locations" class="txt-box">
          <p>{{ location.route }}</p>
          <p>{{ location.city }}</p>
          <p>{{ location.phoneNo }}</p>
        </div>
      </div>
      <div class="column">
        <h3>Working hours</h3>
        <div class="txt-box">
          <h4>monday</h4>
          <p class="txt-red">Kitchen Closed</p>
        </div>
        <div class="txt-box">
          <h4>tuesday until friday</h4>
          <p>9:00 - 22:00</p>
        </div>
        <div class="txt-box">
          <h4>saturday <span class="txt-red">*</span></h4>
          <p>Saturday 11am to midnight</p>
        </div>
        <div class="txt-box">
          <h4>sunday</h4>
          <p>9:00 - 22:00</p>
        </div>
        <div class="txt-box p-top">
          <h4>Follow us:
            <a href="#">
              <img src="../assets/img/iconmonstr-twitter-1-240.png" alt="twitter">
            </a>
            <a href="#">
              <img src="../assets/img/iconmonstr-facebook-1-240.png" alt="facebook">
            </a>
            <a href="#">
              <img src="../assets/img/iconmonstr-instagram-6-240.png" alt="instagram">
            </a>
            <a href="#">
              <img src="../assets/img/iconmonstr-twitter-1-240.png" alt="twitter">
            </a>
          </h4>
        </div>
      </div>
      <div class="column txt-white">
        <h2>
          THE DON PEPPE CREW FIRST AND FOREMOST VALUES AN AUTHENTIC, WELL BAKED SLICE OF PIZZA.
        </h2>
      </div>
      <div class="column-100">
        <p>
          Created with &#9825; by <span>Qode Interactive</span>
        </p>
        <img src="../assets/img/footer-bottom-img.png" alt="quality mark">
      </div>
    </div>
    <div class="wrapper">
      <img src="../assets/img/footer-img-1.jpg" alt="footer img">
    </div>
  </footer>
</template>
<script>
export default {
  data() {
    return {
      locations: [
        {
          route: '1614 E.Bell Rd #104.',
          city: 'Salerno, AZ 85022',
          phoneNo: '(602)857-1010'
        },
        {
          route: '204 E. Pizzetta Tommaso',
          city: 'Sorrenta, AZ 85022',
          phoneNo: '(358)857-1010'
        },
        {
          route: 'Valle Puglia',
          city: 'Torre Del Greco, AZ 85022',
          phoneNo: '(359)857-1010'
        },
        {
          route: 'Corso Itali AA',
          city: 'Naples, AZ 85022',
          phoneNo: '(589)857-1010'
        },
      ]
    }
  },
}
</script>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

footer {
  @include flex(row, flex-start, stretch);

  .wrapper {
    @include flex(row, flex-start, stretch);
    flex-wrap: wrap;
    background-image: url(../assets/img/cielostellato.PNG);
    width: 50%;

    &.link-wrap {
      padding: 12rem 4rem 4rem;
    }

    .column {
      width: calc((100% / 3 - 1rem));
    }

    .column-100 {
      @include flex(row, space-between, flex-end);
      width: 100%;

      p {
        color: $fill-gold;

        span {
          color: $fill-green;
        }
      }
    }

    h3 {
      margin-bottom: 1.3rem;
    }

    .txt-box {
      margin-bottom: 1.3rem;

      &.p-top {
        padding-top: 2.5rem;
      }
    }

    h3,
    h4 {
      text-transform: uppercase;
      color: $fill-gold;

      img {
        display: inline-block;
        line-height: 100px;
        height: 10px;
        margin: 0 .5rem;
      }
    }

    p {
      color: $text-grey;
      font-size: .8rem;
      line-height: 1.5rem;
    }

    .txt-red {
      color: $fill-red;
    }

    .txt-white {
      color: white;
      line-height: 2.2rem;
    }

    >img {
      width: 100%;
    }
  }
}
</style>