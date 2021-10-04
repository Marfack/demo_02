<template>
  <div class="box">
    <div id="pie"></div>
  </div>
</template>

<script>
export default {
  name: 'Pie',
  computed: {
    part() {
      return this.target.map(item => {
        return item.name
      })
    },
    option() {
      return {
        legend: {
          orient: 'vertical',
          x: 'right',
          y: 'center',
          textStyle: {
            color: '#666'
          },
          data: this.part
        },
        series: [
          {
            type: 'pie',
            center: ['50%', '50%'],
            data: this.target,
            emphasis: {
              itemStyle: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: 'rgba(30, 144, 255，0.5)'
              }
            },
            labelLine: {
              show: true
            },
            label: {
              position: 'inner',
              formatter: '{c}'
            }
          }
        ],
      }
    }
  },
  props: {
    target: Array
  },
  mounted() {
    this.$echarts.init(document.getElementById('pie')).setOption(this.option)
  }
}
</script>

<style>
#pie {
  height: 350px;
  width: 400px;
  margin: auto;
}
</style>