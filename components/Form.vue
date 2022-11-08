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
        class="form__message"
      />
      <button class="form__button">Send message</button>
    </div>
  </div>
</template>

<script lang="ts" setup></script>

<style scoped lang="scss">
.form__container {
  margin: 0 $gutter * 2;
}

.form__title {
  font-size: $fontSize * 3;
  text-align: center;
  margin-bottom: $gutter * 8;
  margin-top: $gutter * 10;
  font-family: $fontAlt;
  display: flex;
  justify-content: center;

  &::after {
    content: url('/picture/svg/baseline-contact-mail.svg');
    padding-left: $gutter * 2;
  }
}

.form__button {
  display: flex;
  justify-content: center;
  width: 100%;
  color: #e4e5d6;
  font-family: $fontAlt;
  font-size: $fontSize * 2.3;
  padding: $gutter * 1.95 0;
  background: linear-gradient(#36382e, #21221c);
  margin-top: $gutter * 6;
  border-radius: 8px;

  &::after {
    content: url('/picture/svg/send.svg');
    padding-left: $gutter * 2;
    //transform: translateX(100px);
  }
}

@media screen and (min-width: 1024px) {
  .form {
    background-color: $backgroundContainer;
    border: 1px solid #b7baa6;
    width: 700px;
    height: auto;
    border-radius: 4px;
  }

  .form__container {
    margin: $gutter * 5.3 $gutter * 9 $gutter * 6.5;
  }

  .form__title {
    font-size: $fontSize * 3.4;
    margin-bottom: $gutter * 4.4;

    &::after {
      //width: 39px;
      //height: 29px;
      padding-left: $gutter * 1.4;
    }
  }

  .form__message {
    margin-top: $gutter * 2;
  }
}
</style>
