<template>
  <div class="container">
    <div class="wrapper">
      <input type="text">
      <span>for</span>
      <input type="date" name="booking-date" id="booking-date" placeholder="29/11/2024">
      <span>at</span>
      <input type="time" name="booking-hour" id="booking-hour" placeholder="none">
      <span></span>
      <button>book a table</button>
    </div>
    <p>
      *Powered by OpenTable
    </p>
  </div>
</template>
<script>
export default {
  
}
</script>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

.container{
  background-image: url(../assets/img/h3-background-img-3.jpg);
  background-position: center;
  background-repeat: no-repeat;
  padding: 6rem 0;
  margin-bottom: .5rem;

  .wrapper{
    @include flex(row,center,center);
    width: 70%;
    margin: 0 auto 1rem;


    span{
      text-transform: uppercase;
      width: 60px;
      text-align: center;
      color: white;
      font-weight: 600;
      line-height: 60px;
    }

    input{
      flex-grow: 1;
      height: 60px;
      border: 2px inset black;

      ::placeholder{
        color: white;
      }
    }
    
    button{
      flex-grow: 1.5;
      border: none;
      text-transform: uppercase;
      height: 60px;
      color: white;
      background-color: $fill-red;
    }
  }

  p{
    width: 70%;
    margin: 0 auto;
    color: white;
    font-size: .8rem;
  }
}
  

</style>