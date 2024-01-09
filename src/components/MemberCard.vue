<template>
  <div class="card">
    <img :src="getImageUrl(member.profilePic)" alt="member team">
    <div class="team-hover">
      <div class="caption">
        <h3>{{ member.name }}</h3>
        <p>{{ member.role }}</p>
        <div>
          <a :href="member.social.instagram">
            <img src="../assets/img/iconmonstr-instagram-6-240.png" alt="instagram">
          </a>
          <a :href="member.social.twitter">
            <img src="../assets/img/iconmonstr-twitter-1-240.png" alt="twitter">
          </a>
          <a :href="member.social.facebook">
            <img src="../assets/img/iconmonstr-facebook-1-240.png" alt="facebook">
          </a>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    member: {
      type: Object,
      required: true
    }
  },
  methods: {
    getImageUrl: function (path) {
      return new URL(`../assets/img/${path}`, import.meta.url).href;
    },
  }

}
</script>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

.card {
  position: relative;
  width: 25%;

  &:hover .team-hover {
    display: block;
  }

  img {
    width: 100%;
  }

  .team-hover {
    display: none;
    position: absolute;
    top: 0;
    padding: 1rem;
    width: 100%;
    height: 100%;
    background-image: url(../assets/img/dotted-bgd.png);
    background-size: cover;

    .caption {
      @include flex(column, center, center);
      width: 100%;
      height: 100%;
      background-color: $fill-red;
      color: white;
    }

    h3 {
      text-transform: uppercase;
      margin-bottom: .5rem;
    }

    p {
      text-transform: capitalize;
      margin-bottom: 1rem;
    }

    a {
      padding: .5rem;

      img {
        width: 20px;
      }
    }
  }
}
</style>