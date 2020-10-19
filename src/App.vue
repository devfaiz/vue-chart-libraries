<template>
  <div id="app">
    <section>
      <h2>Chartjs</h2>
      <MonthlySalesChart msg="Welcome to Your Vue.js App"/>
    </section>
    <section>
      <h2>AmCharts</h2>
      <LineChart/>
    </section>
  </div>
</template>

<script>
import MonthlySalesChart from './components/ChartJsExamples/MonthlySalesChart.vue'
import LineChart from './components/AmCharts/LineChart.vue'

export default {
  name: 'App',
  components: {
    MonthlySalesChart,
    LineChart
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
