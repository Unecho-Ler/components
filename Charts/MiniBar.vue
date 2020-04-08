<template>
  <div class="antv-chart-mini">
    <div class="chart-wrapper" :style="{ height: 46 }">
      <v-chart 
        :force-fit="true" 
        :height="height" 
        :data="data" 
        :padding="[36, 5, 18, 5]"
      >
        <v-tooltip />
        <v-bar position="x*y" />
      </v-chart>
    </div>
  </div>
</template>

<script>
import moment from 'moment'
const data = []

data.push({
    x: "CDM",
    y: 20
  },
  {
    x: "CDP",
    y: 4
  },
  {
    x: "灾备",
    y: 7
  },
  {
    x: "存储LUN",
    y: 5
  },
  {
    x: "VTL",
    y: 1
  }
)

const tooltip = [
  'x*y',
  (x, y) => ({
    name: x,
    value: y
  })
]

const scale = [{
  dataKey: 'x',
  min: 0
}, {
  dataKey: 'y',
  title: '数量',
  min: 1,
  max: 30
}]

export default {
  name: 'MiniBar',
  data () {
    return {
      data,
      tooltip,
      scale,
      height: 100
    }
  }
}
</script>

<style lang="less" scoped>
  @import "chart";
</style>
