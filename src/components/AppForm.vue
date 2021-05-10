<template>
  <v-container fluid>
    <v-form
      ref="form"
      v-model="valid"
      lazy-validation
    >
        <form-login-info></form-login-info>

        <form-select-gender></form-select-gender>

        <form-birthday></form-birthday>

        <form-phone-number></form-phone-number>

        <form-check-policy></form-check-policy>

        <form-submit
          v-on:@submitAction="formValidation"
        ></form-submit>
    </v-form>
  </v-container>
</template>

<script>
import FormLoginInfo from './FormLoginInfo';
import FormSelectGender from './FormSelectGender';
import FormBirthday from './FormBirthday';
import FormPhoneNumber from './FormPhoneNumber';
import FormCheckPolicy from './FormCheckPolicy';
import FormSubmit from './FormSubmit';

export default {
  name: 'AppForm',
  data() {
    return {
      valid: false,
    }
  },
  components: {
    'form-login-info': FormLoginInfo,
    'form-select-gender': FormSelectGender,
    'form-birthday': FormBirthday,
    'form-phone-number': FormPhoneNumber,
    'form-check-policy': FormCheckPolicy,
    'form-submit': FormSubmit,
  },
  methods: {
    formValidation() {
      this.$refs.form.validate();
      if (this.valid) {
        alert('가입 완료');
      }
    },
  },
  mounted() {
    this.valid = false;
  },
}
</script>

<style lang="scss" scoped>
</style>