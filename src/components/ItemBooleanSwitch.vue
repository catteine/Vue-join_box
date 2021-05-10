<template>
  <v-switch
    v-model="switchBool"
    :label="thislabel"
    dense
    :rules="[switchBool => !!switchBool || '동의 필요']"
  ></v-switch>
</template>

<script>
export default {
  name: 'ItemBooleanSwitch',
  props : ['checkedBool', 'switchLabel'],
  data() {
    return {
      switchBool: this.checkedBool,
      thislabel: this.switchLabel,
    }
  },
}
</script>

<style lang="scss" scoped>
</style>