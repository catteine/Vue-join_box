<template>
  <v-row class="form-login-info">
    <v-col>
      <item-input-box
        :inputType="text"
        :inputLabel="label_1"
      ></item-input-box>
      <item-input-box
        :inputType="password"
        :inputLabel="label_2"
      ></item-input-box>
    </v-col>
  </v-row>
</template>

<script>
import ItemInputBox from './ItemInputBox';

export default {
  name: 'FormLoginInfo',
  data() {
    return {
      text: "text",
      password: "password",
      label_1: "아이디",
      label_2: "비밀번호",
    }
  },
  components: {
    'item-input-box': ItemInputBox,
  },
}
</script>

<style lang="scss" scoped>
.form-login-info {
  padding-top: 10px;
}
</style>