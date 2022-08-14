<template>
  <chart :chart-data="chartData" />
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  data: () => ({
    chartData: null,
    chart: null,
  }),
  async fetch() {
    this.chartData = await this.$axios.$get(
      'https://europe-west2-nozzle.cloudfunctions.net/api'
    )
  },
})
</script>
