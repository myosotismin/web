<template>
  <div class="box">
    <h2 class="text">固定的子元素</h2>
  </div>
</template>
<script>
export default {
  data() {
    return {}
  },
  created() {},
  computed: {},
  methods: {},
}
</script>
<style scoped>
.box {
  position: fixed;
  top: 60px;
  right: 30px;
  text-align: center;
  width: 100px;
  height: 100px;
  z-index: 999;
  background: rgb(173, 213, 253);
}
.text {
}
</style>
