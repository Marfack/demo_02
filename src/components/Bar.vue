<template>
  <div class="box">
    <div id="bar"></div>
  </div>
</template>

<script>
export default {
  name: 'Bar',
  computed: {
    x: {
      get() {
        return this.target.map(item => {
          return item.name
        })
      }
    },
    y: {
      get() {
        return this.target.map(item => {
          return item.value
        })
      }
    },
    option: {
      get() {
        return {
          tooltip: {
            trigger: 'axis',
            axisPointer: {
              type: 'cross',
              label: {
                backgroundColor: '#DD77DD'
              }
            }
          },
          legend: {},
          xAxis: {
            type: 'category',
            data: this.x,
            axisLabel: {
              interval: 0,
              color: "black",
            }
          },
          yAxis: {
            type: 'value'
          },
          series: [
            {
              data: this.y,
              type: 'bar'
            }
          ]
        }
      }
    }
  },
  props: {
    target: Array
  },
  mounted() {
    this.$echarts.init(document.getElementById('bar')).setOption(this.option)
  }
}
</script>

<style>
#bar {
  height: 350px;
  width: 400px;
  margin: auto;
}
</style>