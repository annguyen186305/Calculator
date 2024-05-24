<template>
  <div class="calculator">
    <p>casio fx-570</p>
    <input v-model="display" readonly/>

    <div class="buttons">
      <NutBanPhim v-for="(cacNut, index) in danhSachNut"
                  :key="index"
                  :nut="cacNut.nut"
                  @nutHienThi="hienThiSo"
                  @nutXoaManHinh="xoaManHinh"
                  @nutTinhToan="tinhToan">
      </NutBanPhim>
    </div>
  </div>
</template>

<script>
import NutBanPhim from "@/components/NutBanPhim.vue";

export default {
  name: 'MayTinhCamTay',
  components: {
    NutBanPhim
  },
  data () {
    return {
      display: '',
      danhSachNut:[
        {nut:'1'},
        {nut:'2'},
        {nut:'3'},
        {nut:'4'},
        {nut:'5'},
        {nut:'6'},
        {nut:'7'},
        {nut:'8'},
        {nut:'9'},
        {nut:'0'},
        {nut:'+'},
        {nut:'-'},
        {nut:'*'},
        {nut:'/'},
        {nut:'C'},
        {nut:'='},
      ]
    }
  },
  methods: {
    hienThiSo(nut) {
      this.display += nut;
    },
    xoaManHinh() {
      this.display = '';
    },
    tinhToan() {
      try {
        this.display = eval(this.display).toString();
      } catch (e) {
        this.display = 'Error';
      }
    }
  }
};
</script>

<style scoped>
.calculator {
  padding: 10px;
  margin: auto;
  margin-top: 20px;
  width: 300px;
  background-color: yellow;
  border-radius: 20px;
}
input {
  width: 250px;
  height: 40px;
  text-align: right;
  margin-bottom: 10px;
  border-radius: 10px;
}
.buttons {
  margin-top: 20px;
  margin-left: 10px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}
</style>