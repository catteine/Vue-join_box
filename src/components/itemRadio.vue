<template>
  <v-radio-group
    ref="radios"
    v-model="defaultChecked"
    row
    dense
  >
    <v-radio
      v-for="radioItem in radioItems"
      :key="radioItem"
      :label="radioItem"
      :value="radioItem"
    ></v-radio>
  </v-radio-group>
</template>

<script>
export default {
  name: 'itemRadio',
  props : ['selectionList'],
  data () {
    return {
      radioItems: this.selectionList,
      defaultChecked: this.selectionList[0],
    }
  },
}
</script>

<style lang="scss" scoped>
.v-input--selection-controls {
  margin-top: 0;
}
</style>