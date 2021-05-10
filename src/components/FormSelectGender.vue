<template>
  <v-row class="form-gender">
    <v-col>
      <item-radio
        :selectionList="thisList"
      ></item-radio>
    </v-col>
  </v-row>
</template>

<script>
import itemRadio from './itemRadio';

export default {
  name: 'FormSelectGender',
  data() {
    return {
      thisList: ['남자', '여자'],
    }
  },
  components: {
    'item-radio': itemRadio,
  },
}
</script>

<style lang="scss" scoped>
</style>