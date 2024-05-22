<template>
  <div>
    <button @click="nhapSoTuNut">{{ nut }}</button>
  </div>
</template>

<script>
export default {
  name: 'NutBanPhim',
  props: {
    nut: String
  },
  methods: {
    nhapSoTuNut() {
      this.$emit('nutHienThi', this.nut);
    }
  }
}
</script>

<style scoped>
button {
  width: 40px;
  height: 40px;
  font-size: 14px;
}
</style>