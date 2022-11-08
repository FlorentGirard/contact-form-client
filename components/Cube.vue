<template>
  <div class="square">
    <div class="square__cube square__cube--topLeft"></div>
    <div class="square__cube square__cube--topLeft2"></div>
    <div class="square__cube square__cube--topLeft3"></div>

    <div class="square__cube square__cube--topRight"></div>
    <div class="square__cube square__cube--topRight2"></div>
    <div class="square__cube square__cube--topRight3"></div>

    <div class="square__cube square__cube--bottomLeft"></div>
    <div class="square__cube square__cube--bottomLeft2"></div>
    <div class="square__cube square__cube--bottomLeft3"></div>

    <div class="square__cube square__cube--bottomRight"></div>
    <div class="square__cube square__cube--bottomRight2"></div>
    <div class="square__cube square__cube--bottomRight3"></div>
  </div>
</template>

<script lang="ts" setup></script>

<style scoped lang="scss">
.square__cube {
  width: 100px;
  height: 100px;
  position: absolute;
  z-index: -1;

  &--topLeft {
    top: 0;
    left: 0;
    background-color: #f7f7f3;
  }

  &--topLeft2 {
    background-color: #caccb3;
    top: 0;
    left: 100px;
  }

  &--topLeft3 {
    top: 100px;
    left: 0;
    background-color: #bcbe9d;
  }

  &--topRight {
    top: 0;
    right: 0;
    background-color: #e9e9e2;
  }

  &--topRight2 {
    top: 0;
    right: 100px;
    background-color: #d5d6c2;
  }

  &--topRight3 {
    top: 100px;
    right: 0;
    background-color: #c1c3a2;
  }

  &--bottomLeft {
    bottom: 0;
    left: 0;
    background-color: #e0e1d2;
  }

  &--bottomLeft2 {
    bottom: 0;
    left: 100px;
    background-color: #d5d6c2;
  }

  &--bottomLeft3 {
    bottom: 100px;
    left: 0;
    background-color: #caccb3;
  }

  &--bottomRight {
    right: 0;
    bottom: 0;
    background-color: #abad85;
  }

  &--bottomRight2 {
    right: 100px;
    bottom: 0;
    background-color: #dfe0d1;
  }
  &--bottomRight3 {
    right: 0;
    bottom: 100px;
    background-color: #fafaf7;
  }
}
</style>
