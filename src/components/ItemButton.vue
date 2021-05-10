<template>
  <v-btn
    :type="thisType"
    ref="button"
    color="primary"
    depressed
    large
    width="100%"
    height="40px"
    v-on:click.prevent="thisMethod"
    :disabled="thisDisabled"
  >
    <slot></slot>
  </v-btn>
</template>

<script>
export default {
  name: 'ItemButton',
  props: ['buttonType', 'isDisable'],
  data() {
    return {
      thisType: this.buttonType,
      thisDisabled: this.isDisable,
    }
  },
  methods: {
    thisMethod() {
      this.$emit('@buttonMethod');
    },
  },
  watch: {
    isDisable: function() {
      this.thisDisabled = this.isDisable;
    },
  },
}
</script>

<style lang="scss" scoped>
button {
  min-width: 0 !important;
  padding: 0 !important;
}
</style>