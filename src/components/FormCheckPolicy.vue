<template>
  <v-row class="form-check-policy">
    <v-col>
      <item-boolean-switch
        :checkedBool="defaultBool"
        :switchLabel="label"
      ></item-boolean-switch>
    </v-col>
  </v-row>
</template>

<script>
import ItemBooleanSwitch from './ItemBooleanSwitch';

export default {
  name: 'FormCheckPolicy',
  data() {
    return {
      defaultBool: false,
      label: "모든 약관 내용에 동의합니다.",
    }
  },
  components: {
    'item-boolean-switch': ItemBooleanSwitch,
  },
}
</script>

<style lang="scss" scoped>
</style>