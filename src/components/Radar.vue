<template>
  <div class="box" v-if="target != undefined">
    <div id="radar"></div>
  </div>
</template>

<script>
export default {
  name: 'Radar',
  computed: {
    indicator: {
      get() {
        return this.target.map(item => {
          return {
            text: item.name,
            max: 5.0
          }
        })
      }
    },
    data: {
      get() {
        return [
          {
            name: 'radar',
            value: this.target.map(item => {
              return item.value
            })
          }
        ]
      }
    },
    option: {
      get() {
        return {
          color: ['#67F9D8', '#FFE434', '#56A3F1', '#FF917C'],
          radar: [
            {
              indicator: this.indicator,
              center: ['50%', '50%'],
              // radius: 120,
              startAngle: 90,
              splitNumber: 4,
              // shape: 'circle',
              axisName: {
                formatter: '{value}',
                color: '#428BD4'
              },
              splitArea: {
                areaStyle: {
                  color: ['#77EADF', '#26C3BE', '#64AFE9', '#428BD4'],
                  shadowColor: 'rgba(0, 0, 0, 0.2)',
                  shadowBlur: 10
                }
              },
              axisLine: {
                lineStyle: {
                  color: 'rgba(211, 253, 250, 0.8)'
                }
              },
              splitLine: {
                lineStyle: {
                  color: 'rgba(211, 253, 250, 0.8)'
                }
              }
            }
          ],
          series: [
            {
              type: 'radar',
              emphasis: {
                lineStyle: {
                  width: 4
                }
              },
              data: this.data
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
    this.$echarts.init(document.getElementById('radar')).setOption(this.option)
  }
}
</script>

<style scoped>
.box {
  height: 100%;
}
#radar {
  width: 500px;
  height: 500px;
  margin: auto;
}
</style>