<template>
  <div class="container">
    <div class="wrapper bg-star">
      <span>
        made with love
      </span>
      <h1>delish pizza deals</h1>
      <div v-for="(event, index) in events" class="event" :class="(index < events.length - 1) ? 'border-dotted' : ''">
        <div class="left">
          <span class="txt-big">{{ event.day }}</span>
          <p>{{ event.month }}</p>
        </div>
        <div class="right">
          <p>{{ event.name }}</p>
          <span>
            <img src="../assets/img/iconmonstr-location-1-240.png" alt="location pin">
            {{ event.location }}
          </span>
        </div>
      </div>
    </div>
    <div class="wrapper">
      <img src="../assets/img/h3-img-5a.jpg" alt="">
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      events:[
        {
          day:'02',
          month:'nov',
          name:'TRADITIONAL NEAPOLITAN PIES IN KYOTO PIZZA MERCATO',
          location:'204 E.pizzetta Tommaso'
        },
        {
          day:'03',
          month:'nov',
          name:'TERRAZZA PATIO DINING SPACE OPENING THIS WEEKEND',
          location:'204 E.pizzetta Tommaso'
        },
        {
          day:'05',
          month:'nov',
          name:'SIENNA PRIVATE DINING ROOM WITH STÉPHANE BRUNN',
          location:'204 E.pizzetta Tommaso'
        },
      ]
    }
  },
}
</script>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

.container{
@include flex(row,center,flex-start);
margin-bottom: .5rem;

  .wrapper{
    width: 50%;
    height: 100%;
    
    &.bg-star{
      padding: 6rem 10rem;
      background-image: url(../assets/img/cielostellato.PNG);
      
      h1{
        color: white;
        font-size: 2.5rem;
        text-transform: uppercase;
        margin: .5rem 0 2rem;
      }
      
      p{
        text-transform: uppercase;
        color: white;
        font-weight: 600;
      }
      .event{
        @include flex(row,flex-start,flex-start);
        padding: 2rem 0;
        max-width: 500px;

        &.border-dotted{
          border-bottom: 1px dotted $fill-gold;
        }

        p{
          font-size: 1.3rem;
        }

        .left{
          text-align: center;
          margin-right: 2.5rem;
        }

        .right{
          padding-top: .6rem;

          span{
            display: inline-block;
            padding-top: 1rem;
            font-size: .8rem;
            vertical-align: middle;
            
            img{
              margin: 0 .33rem .2rem 0 ;
              vertical-align: middle;
              display: inline-block;
              height: 15px;
            }
          }
        }
      }
      
      span{
        color: $fill-red;
        font-size: .8rem;
        font-weight: 600;
        text-transform: uppercase;
        &.txt-big{
          display: inline-block;
          font-weight: 700;
          font-size: 3rem;
        }
        
      }
      
    }

    img{
      display: block;
    }
  }
}
  
</style>