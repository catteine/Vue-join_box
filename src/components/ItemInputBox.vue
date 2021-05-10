<template>
  <v-text-field
    ref="textField"
    v-model="thisValue"
    :label="thisLabel"
    :type="thisType"
    :maxlength="limit"
    outlined
    solo
    flat
    dense
    class="body-2"
    :rules="[thisValue => !!thisValue || '입력 필요']"
    @keyup="keyupEvent"
  ></v-text-field>
</template>

<script>
export default {
  name: 'ItemInputBox',
  props : ['inputType', 'inputLabel', 'maxLength'],
  data() {
    return {
      thisValue: "",
      thisType: this.inputType,
      thisLabel: this.inputLabel,
      limit: this.maxLength,
    }
  },
  methods : {
    keyupEvent() {
      this.$emit('@keyupMethod', this.$refs.textField);
    },
  },
}
</script>

<style lang="scss" scoped>
</style>