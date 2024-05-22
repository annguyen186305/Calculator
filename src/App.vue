<template>
  <div id="app">
    <MayTinhCamTay/>
  </div>
</template>
<script>
import MayTinhCamTay from "@/components/Caculator.vue";
export default {
  name: 'App',
  components: {
    MayTinhCamTay,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
