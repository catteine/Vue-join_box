<template>
  <v-row class="form-submit">
    <v-col>
      <item-button
        :buttonType="button"
        v-on:@buttonMethod="formValidation"
      >가입하기</item-button>
    </v-col>
  </v-row>
</template>

<script>
import ItemButton from './ItemButton';

export default {
  name: 'FormSubmit',
  data() {
    return {
      button: "submit",
    }
  },
  components: {
    'item-button': ItemButton,
  },
  methods : {
    formValidation() {
      this.$emit('@submitAction');
    },
  },
}
</script>

<style lang="scss" scoped>

</style>