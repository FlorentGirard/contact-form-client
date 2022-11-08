<template>
  <div class="home">
    <h1 class="home__title">Contact us</h1>
    <div class="home__cube home__cube--top"></div>
    <Cube />
    <div class="home__container">
      <Form />
      <div class="home__vector">
        <div class="home__contact">
          <div class="home__flex">
            <button class="home__button">
              <img src="/picture/svg/email.svg" alt="email" />
            </button>
            <div class="home__cube"></div>
          </div>
          <div class="home__flex">
            <button class="home__button">
              <img src="/picture/svg/phone.svg" alt="phone" />
            </button>
            <div class="home__cube home__cube--big"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup></script>

<style scoped lang="scss">
.home__vector,
.home__title,
.home__cube {
  display: none;
}
@media screen and (min-width: 1024px) {
  .home {
    position: relative;
    height: 100vh;
  }

  .home__cube {
    display: block;
  }

  .home__title {
    display: block;
    font-size: $fontSize * 30;
    white-space: nowrap;
    color: #3a3c33;
    opacity: 0.04;
    font-family: $fontAlt;
    vertical-align: top;
    margin-left: 170px;
    line-height: 0.7;
  }

  .home__cube {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    background: linear-gradient($colorLight 100%, $colorLight 33%);

    &--top {
      position: absolute;
      top: 10px;
      left: 550px;
    }

    &--big {
      width: 160px;
      height: 160px;
    }
  }

  .home__button {
    padding-right: $gutter * 6;
  }

  .home__contact {
    display: flex;
    justify-content: space-between;
    margin-right: $gutter * 10;
    transform: translateY(-50px);
  }

  .home__flex {
    display: flex;
    align-items: center;
  }

  .home__container {
    display: flex;
    align-items: center;
    // height: 100vh;
    margin-left: $gutter * 24.2;
  }

  .home__vector {
    display: block;
    width: 50%;
    height: 500px;
    background: top / contain no-repeat url('/picture/Vector.png');
    margin-left: $gutter * 9.5;
  }
}
</style>
