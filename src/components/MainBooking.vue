<template>
  <div class="container">
    <div class="wrapper">
      <div class="input-wrap">
        <input type="text" name="booking-person" id="booking-person" placeholder="1 Person">
        <img src="../assets/img/iconmonstr-user-6-240.png" alt="person">
        <p>
          *Powered by OpenTable
        </p>
      </div>
      <span>for</span>
      <div class="input-wrap">
        <input type="date" name="booking-date" id="booking-date" v-model="myDate">
        <img src="../assets/img/iconmonstr-calendar-thin-240.png" alt="calendar">
      </div>
      <span>at</span>
      <div class="input-wrap">
        <input type="time" name="booking-hour" id="booking-hour" v-model="myTime">
        <img src="../assets/img/iconmonstr-time-9-240.png" alt="clock">
      </div>
      <span></span>
      <div>
        <button>book a table</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      myDate: new Date().toISOString().slice(0, 10),
      myTime: '09:00',
    }
  },
}
</script>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

.container {
  background-image: url(../assets/img/h3-background-img-3.jpg);
  background-position: center;
  background-repeat: no-repeat;
  padding: 6rem 0;
  margin-bottom: .5rem;

  .wrapper {
    @include flex(row, center, flex-start);
    padding-top: 1.3rem;

    .input-wrap{
      position: relative;

      img{
        position: absolute;
        height: 18px;
        top: 30px;
        transform: translateY(-50%);
        right: 1rem;
      }
    }

    span {
      text-transform: uppercase;
      width: 60px;
      text-align: center;
      color: white;
      font-weight: 600;
      line-height: 60px;
    }

    input {
      width: 250px;
      height: 60px;
      padding: 1.2rem;
      border: 2px inset black;
      color: $text-grey;

      &::placeholder {
        color: $text-grey;
      }
      &::-webkit-calendar-picker-indicator {
        opacity: 0;
      }
    }


    button {
      width: 250px;
      border: none;
      text-transform: uppercase;
      height: 60px;
      font-size: .8rem;
      font-weight: 600;
      color: white;
      background-color: $fill-red;
    }

    p {
      padding-top: .5rem;
      color: white;
      font-size: .8rem;
    }
  }

}
</style>