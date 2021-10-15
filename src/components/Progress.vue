<template>
  <div class="box">
    <div class="item" v-for="(item, index) in target" :key="index">
      <span style="flex: 1; font-size: 20px">{{item.name}}</span>
      <el-progress style="flex: 6" :stroke-width="30" :percentage="item.value" :color="randomColor()"/>
    </div>
  </div>
</template>

<script>
export default {
  name: "Progress",
  props: {
    target: Array
  },
  methods: {
    randomColor() {
      return 'rgb(' + Math.round(Math.random() * 255) + ',' + Math.round(Math.random() * 255) + ',' + Math.round(Math.random() * 255) + ')'
    }
  }
}
</script>

<style scoped>
.box {
  width: 100%;
  height: 100%;
}

.item {
  margin: 23px 0;
  padding: 0 20px;
  display: flex;
}
</style>