<template>
  <div class="box">
    <div id="line"></div>
  </div>
</template>

<script>
export default {
  name: 'Line',
  computed: {
    time() {
      return this.target[0].value.map(item => {
        return item.time
      })
    },
    series() {
      return this.target.map(item => {
        return {
          name: item.name,
          type: 'line',
          data: item.value.map(i => {
            return i.value
          }),
          itemStyle: {
            color: 'rgb(' + Math.round(Math.random() * 200) + ',' + Math.round(Math.random() * 200) + ',' + Math.round(Math.random() * 200) + ')'
          }
        }
      })
    },
    option() {
      return {
        tooltip: {
          trigger: 'axis',
          axisPointer: {
            type: 'cross',
            label: {
              backgroundColor: '#6a7985'
            }
          }
        },
        legend: {
          orient: 'vertical',
          x: 'right',
          y: 'center'
        },
        xAxis: {
          data: this.time,
          axisLabel: {
            interval: 0,
            color: "black",
            rotate:30
          }
        },
        yAxis: {
          min: 0,
          max: 5
        },
        series: this.series
      }
    }
  },
  props: {
    target: Array
  },
  mounted() {
    this.$echarts.init(document.getElementById('line')).setOption(this.option)
  }
}
</script>

<style>
#line {
  height: 350px;
  width: 400px;
  margin: auto;
}
</style>