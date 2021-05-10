<template>
  <v-row class="form-phone-number flex-nowrap" no-gutters>
    <v-col cols="1">
      <v-subheader class="subtitle-2">전화</v-subheader>
    </v-col>
    <v-col>
      <!-- 앞자리 선택 -->
      <item-selectbox
        :selectOptions="firstNumber"
        :selectLabel="label_1"
        :checkedOption="checkedItem"
      ></item-selectbox>
    </v-col>
    <v-col>
      <!-- 나머지 번호 입력 -->
      <item-input-box
        :inputType="number"
        :inputLabel="label_2"
        :maxLength="textMaxLength"
        v-on:@keyupMethod="checkEmpty"
      ></item-input-box>
    </v-col>
    <v-col>
      <!-- 인증 버튼 -->
      <item-button
        :buttonType="button"
        :isDisable="btnDisabled"
        v-on:@buttonMethod="notiCertification"
      >인증</item-button>
    </v-col>
  </v-row>
</template>

<script>
import ItemSelectBox from './ItemSelectBox';
import ItemInputBox from './ItemInputBox';
import ItemButton from './ItemButton';

export default {
  name: 'FormPhoneNumber',
  data() {
    return {
      firstNumber: [],
      label_1: "앞자리",
      checkedItem: "",
      number: "tel",
      label_2: "번호 입력",
      button: "button",
      textMaxLength: "8",
      btnDisabled: true,
    }
  },
  components: {
    'item-selectbox': ItemSelectBox,
    'item-input-box': ItemInputBox,
    'item-button': ItemButton,
  },
  created() {
    // 전화번호 앞자리 배열 세팅
    this.firstNumber = ['010', '011', '016'];
    this.checkedItem =  this.firstNumber[0];
  },
  methods: {
    notiCertification() {
      alert('인증 완료');
    },
    checkEmpty(thisInput) {
      if (thisInput.value != "") {
        this.btnDisabled = false;
      } else {
        this.btnDisabled = true;
      }
    },
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
  &:nth-child(3) {
    min-width: 150px;
  }
}
</style>