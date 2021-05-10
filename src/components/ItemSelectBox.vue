<template>
  <v-select
    ref="selectBox"
    v-model="checkedItem"
    :items="thisOptions"
    :label="thisLabel"
    outlined
    solo
    flat
    dense
    :rules="[checkedItem => !!checkedItem || '입력 필요']"
  ></v-select>
</template>

<script>
export default {
  name: 'ItemSelectBox',
  props : ['selectOptions', 'selectLabel', 'checkedOption'],
  data() {
    return {
      thisOptions: this.selectOptions,
      thisLabel: this.selectLabel,
      checkedItem: this.checkedOption,
    }
  },
}
</script>

<style lang="scss" scoped>
</style>