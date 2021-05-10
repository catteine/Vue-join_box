<template>
  <v-row class="form-birthday" no-gutters>
    <v-col cols="1">
      <v-subheader class="subtitle-2">생일</v-subheader>
    </v-col>
    <v-col>
      <!-- 년 -->
      <item-selectbox
        :selectOptions="optionYear"
        :selectLabel="label_1"
      ></item-selectbox>
    </v-col>
    <v-col>
      <!-- 월 -->
      <item-selectbox
        :selectOptions="optionMonth"
        :selectLabel="label_2"
      ></item-selectbox>
    </v-col>
    <v-col>
      <!-- 일 -->
      <item-selectbox
        :selectOptions="optionDay"
        :selectLabel="label_3"
      ></item-selectbox>
    </v-col>
  </v-row>
</template>

<script>
import ItemSelectBox from './ItemSelectBox';

export default {
  name: 'FormBirthday',
  data() {
    return {
      optionsYear: [],
      optionsMonth: [],
      optionsDay: [],
      label_1: '년',
      label_2: '월',
      label_3: '일',
    }
  },
  components: {
    'item-selectbox': ItemSelectBox,
  },
  created() {
    // 년 채우기
    this.optionYear = (() => {
      let arr = [];
      for(let i = 1900; i <= 2020; i++) {
        arr.unshift(i);
      }
      return arr;
    })();
    // 월 채우기
    this.optionMonth = (() => {
      let arr = [];
      for(let i = 1; i <= 12; i++) {
        arr.push(i);
      }
      return arr;
    })();
    // 일 채우기
    this.optionDay = (() => {
      let arr = [];
      for(let i = 1; i <= 31; i++) {
        arr.push(i);
      }
      return arr;
    })();
  },
}
</script>

<style lang="scss" scoped>
.v-subheader {
  height: 40px;
  padding: 0;
}
.col {
  padding:0 0 0 10px;
  &:first-child {
    min-width: 30px;
    padding-left: 0;
  }
}
</style>