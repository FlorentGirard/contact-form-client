<template>
  <div class="form">
    <div class="form__container">
      <h2 class="form__title">
        Contact us <span class="form__title--svg"></span>
      </h2>
      <BaseInput label="Name" placeholder="Enter your Name" type="text" />
      <BaseInput label="Email" placeholder="Enter your Email" type="email" />
      <BaseInput
        label="Phone Number"
        placeholder="Enter your phone number"
        type="text"
      />
      <BaseMessage
        label="Message"
        placeholder="Enter your message"
        size="500"
      />
    </div>
  </div>
</template>

<script lang="ts" setup></script>

<style scoped lang="scss">
.form {
  background-color: $backgroundContainer;
  width: 700px;
  height: 600px;
}

.form__container {
  margin: $gutter * 5.3 $gutter * 9 $gutter * 6.5;
}

.form__title {
  font-weight: 700;
  font-size: $fontSize * 3.4;
  display: flex;
  margin-bottom: $gutter * 4.4;

  &::after {
    content: url('/picture/svg/baseline-contact-mail.svg');
    width: 39px;
    height: 29px;
    padding-left: $gutter * 1.4;
  }
}
</style>
