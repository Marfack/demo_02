<template>
  <div id="frame">
    <el-row :gutter="20" class="el-row">
      <el-col :span="18">
        <el-row :gutter="20" class="el-row">
          <el-col :span="8"><my-title></my-title></el-col>
          <el-col :span="16 / titleTarget.length" v-for="(item, index) in titleTarget" :key="index">
            <title-item :target="item"></title-item>
          </el-col>
        </el-row>
        <el-row :gutter="20" class="el-row">
          <el-col :span="16"><bar :target="barTarget"></bar></el-col>
          <el-col :span="8"><my-data :target="dataTarget"></my-data></el-col>
        </el-row>
        <el-row :gutter="20" class="el-row">
          <el-col :span="16"><my-line :target="lineTarget"></my-line></el-col>
          <el-col :span="8"><pie :target="pieTarget"></pie></el-col>
        </el-row>
      </el-col>
      <el-col :span="6">
        <el-row class="el-row" style="height: 48%">
          <radar :target="radarTarget"></radar>
        </el-row>
        <el-row class="el-row" style="height: 48%; margin-top: 21px">
          <my-progress :target="progressTarget"></my-progress>
        </el-row>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import MyTitle from './Title'
import TitleItem from './TitleItem'
import Radar from './Radar'
import MyData from './Data'
import Bar from './Bar'
import MyLine from './Line'
import Pie from './Pie'
import MyProgress from './Progress'
import titleTarget from '@/assets/json/target/title-target.json'
import radarTarget from '@/assets/json/target/radar-target.json'
import dataTarget from '@/assets/json/target/data-target.json'
import barTarget from '@/assets/json/target/bar-target.json'
import lineTarget from '@/assets/json/target/line-target.json'
import pieTarget from '@/assets/json/target/pie-target.json'
import progressTarget from '@/assets/json/target/progress-target.json'

export default {
  name: 'Frame',
  components: {
    MyTitle,
    TitleItem,
    Radar,
    MyData,
    Bar,
    MyLine,
    Pie,
    MyProgress
  },
  data() {
    return {
      radarTarget,
      dataTarget,
      barTarget,
      lineTarget,
      pieTarget,
      titleTarget,
      progressTarget
    }
  }
}
</script>

<style>
#frame {
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