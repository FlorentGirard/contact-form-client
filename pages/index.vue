<template>
  <div class="home">
    <Cube />
    <div class="home__container">
      <Form />
      <div class="home__vector"></div>
    </div>
  </div>
</template>

<script lang="ts" setup></script>

<style scoped lang="scss">
.home {
  position: relative;
  height: 100vh;
}

.home__container {
  display: flex;
  align-items: center;
  height: 100vh;
  margin-left: $gutter * 24.2;
}

.home__vector {
  width: 1283px;
  height: 668px;
  background: center / cover no-repeat url('/picture/Vector.jpg');
}
</style>
