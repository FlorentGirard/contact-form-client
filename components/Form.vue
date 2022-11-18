<template>
  <div class="form">
    <div class="form__container">
      <h2 class="form__title">
        Contact us <span class="form__title--svg"></span>
      </h2>
      <form @submit.prevent="submit">
        <fieldset>
          <legend class="hide">Name</legend>
          <BaseInput
            v-model="name"
            label="Name"
            placeholder="Enter your Name"
            :error="errors.name"
            type="text"
          />
        </fieldset>
        <fieldset>
          <legend class="hide">Email</legend>
          <BaseInput
            v-model="email"
            label="Email"
            placeholder="Enter your Email"
            type="email"
            :error="errors.email"
          />
        </fieldset>
        <fieldset>
          <legend class="hide">Phone number</legend>
          <BaseInput
            v-model="phone"
            label="Phone Number"
            placeholder="Enter your phone number"
            type="text"
            :error="errors.phone"
          />
        </fieldset>
        <fieldset>
          <legend class="hide">Message</legend>
          <BaseTextArea
            v-model="message"
            label="Message"
            placeholder="Enter your message"
            class="form__message"
            :error="errors.message"
          />
        </fieldset>
        <button type="submit" class="form__button">Send message</button>
      </form>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { object, string } from 'yup'
import { useField, useForm } from 'vee-validate'

const phoneRegExp =
  /^((\\+[1-9]{1,4}[ \\-]*)|(\\([0-9]{2,3}\\)[ \\-]*)|([0-9]{2,4})[ \\-]*)*?[0-9]{3,4}?[ \\-]*[0-9]{3,4}?$/

const validationSchema = object({
  name: string().required().min(3),
  phone: string().matches(phoneRegExp, 'Phone number is not valid'),
  email: string().email().required('email'),
  message: string().required('message'),
})

const { handleSubmit, errors } = useForm({
  validationSchema,
})

const { value: name } = useField('name')
const { value: email } = useField('email')
const { value: phone } = useField('phone')
const { value: message } = useField('message')
const submit = handleSubmit((values) => {
  console.log('envoyé', values)

  //! axios
})
</script>

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

    margin-bottom: $gutter * 3;
    margin-top: $gutter * 3;

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
