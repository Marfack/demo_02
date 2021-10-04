<template>
  <div class="box" v-if="target != undefined">
    <el-table :data="target" stripe height="100%">
      <el-table-column prop="name" align="left" class-name="table-item"></el-table-column>
      <el-table-column prop="value" align="right" class-name="table-item"></el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  name: 'Data',
  props: {
    target: Array
  }
}
</script>

<style>
.table-item {
  font-size: 20px;
  height: 55px;
  font-family: 'Helvetica Neue', Helvetica, 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', '微软雅黑', Arial, sans-serif;
}
</style>