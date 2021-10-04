<template>
  <div id="frame">
    <el-row class="el-row">
      <el-col :span="24"><my-title></my-title></el-col>
    </el-row>
    <el-row :gutter="20" class="el-row">
      <el-col :span="12"><radar :target="radarTarget"></radar></el-col>
      <el-col :span="12"><my-data :target="dataTarget"></my-data></el-col>
    </el-row>
    <el-row :gutter="20" class="el-row">
      <el-col :span="8"><pie :target="pieTarget"></pie></el-col>
      <el-col :span="8"><bar :target="barTarget"></bar></el-col>
      <el-col :span="8"><my-line :target="lineTarget"></my-line></el-col>
    </el-row>
  </div>
</template>

<script>
import MyTitle from './Title'
import Radar from './Radar'
import MyData from './Data'
import Bar from './Bar'
import MyLine from './Line'
import Pie from './Pie'
import radarTarget from '@/assets/json/target/radar-target.json'
import dataTarget from '@/assets/json/target/data-target.json'
import barTarget from '@/assets/json/target/bar-target.json'
import lineTarget from '@/assets/json/target/line-target.json'
import pieTarget from '@/assets/json/target/pie-target.json'

export default {
  name: 'Frame',
  components: {
    MyTitle,
    Radar,
    MyData,
    Bar,
    MyLine,
    Pie
  },
  data() {
    return {
      radarTarget,
      dataTarget,
      barTarget,
      lineTarget,
      pieTarget
    }
  }
}
</script>

<style>
#frame {
  width: 70%;
  margin: auto;
  background-color: #fff
}

.el-row {
  margin-bottom: 20px;
  flex-wrap: wrap
}

.box {
  height: 100%;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
}
</style>