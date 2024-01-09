<template>
  <div class="container">
    <div class="wrapper">
      <MemberCard v-for="member in team"
      :member="member"
      />
    </div>
    <div class="wrapper bg-light">
      <a v-for="client in clients" :href="client.link">
      <img :src="getImageUrl(client.src)" alt="client.clientName">
      </a>
    </div>
  </div>
</template>
<script>
import MemberCard from './MemberCard.vue';

export default {
  data() {
    return {
      team:[
        {
          profilePic:'h1-team-1a-700x700.jpg',
          name:'Frank Bailey',
          role:'Kitchen Porter',
          social:{
            instagram:'#',
            twitter:'#',
            facebook:'#'
          }
        },
        {
          profilePic:'h1-team-2a.jpg',
          name:'Ashley Mc Gregor',
          role:'waitress',
          social:{
            instagram:'#',
            twitter:'#',
            facebook:'#'
          }
        },
        {
          profilePic:'h1-team-3a.jpg',
          name:'Jessee Portland',
          role:'Marketing',
          social:{
            instagram:'#',
            twitter:'#',
            facebook:'#'
          }
        },
        {
          profilePic:'h1-team-4a.jpg',
          name:'Jonathan Bailey',
          role:'chef',
          social:{
            instagram:'#',
            twitter:'#',
            facebook:'#'
          }
        },
      ],
      clients:[
        {
          clientName:'abc',
          src:'h1-clients-img-4.png',
          link:'#'
        },
        {          
          clientName:'abc',
          src:'h1-clients-img-3.png',
          link:'#'  
        },
        {
          clientName:'abc',
          src:'h1-clients-img-1.png',
          link:'#'  
        },
        {
          clientName:'abc',
          src:'h1-clients-img-2.png',
          link:'#'  
        },
        {
          clientName:'abc',
          src:'h1-clients-img-5.png',
          link:'#'  
        },
      ]
    }
  },
  components:{
    MemberCard
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
  
.wrapper{
  @include flex(row,center,center);
  margin-bottom: .5rem;

  &.bg-light{
    padding: 5rem 0;
    background-color: $bg-light;

    img{
      width: 250px;
    }
  }
}

</style>