<template>
  <div class="calculator">
    <p>casio fx-570</p>
    <input v-model="display" readonly/>

    <div class="buttons">
      <NutBanPhim nut="1" @nutHienThi="hienThiSo"></NutBanPhim>
      <NutBanPhim nut="2" @nutHienThi="hienThiSo"></NutBanPhim>
      <NutBanPhim nut="3" @nutHienThi="hienThiSo"></NutBanPhim>
      <NutBanPhim nut="4" @nutHienThi="hienThiSo"></NutBanPhim>
      <NutBanPhim nut="5" @nutHienThi="hienThiSo"></NutBanPhim>
      <NutBanPhim nut="6" @nutHienThi="hienThiSo"></NutBanPhim>
      <NutBanPhim nut="7" @nutHienThi="hienThiSo"></NutBanPhim>
      <NutBanPhim nut="8" @nutHienThi="hienThiSo"></NutBanPhim>
      <NutBanPhim nut="9" @nutHienThi="hienThiSo"></NutBanPhim>
      <NutBanPhim nut="0" @nutHienThi="hienThiSo"></NutBanPhim>
      <NutBanPhim nut="+" @nutHienThi="hienThiSo"></NutBanPhim>
      <NutBanPhim nut="-" @nutHienThi="hienThiSo"></NutBanPhim>
      <NutBanPhim nut="*" @nutHienThi="hienThiSo"></NutBanPhim>
      <NutBanPhim nut="/" @nutHienThi="hienThiSo"></NutBanPhim>
      <NutBanPhim nut="C" @nutHienThi="xoaManHinh"></NutBanPhim>
      <NutBanPhim nut="=" @nutHienThi="tinhToan"></NutBanPhim>
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
      display: ''
    };
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