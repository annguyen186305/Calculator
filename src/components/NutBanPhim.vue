<template>
  <div>
    <button @click="nutDuocChon">{{ nut }}</button>
  </div>
</template>

<script>
export default {
  name: 'NutBanPhim',
  props: {
    nut: String
  },
  methods: {
    nutDuocChon() {
        if (this.nut === 'C')
          {
            this.$emit('nutXoaManHinh');
          }
        else if (this.nut === '=')
          {
            this.$emit('nutTinhToan');
          }
        else
          {
            this.$emit('nutHienThi', this.nut);
          }
    },
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