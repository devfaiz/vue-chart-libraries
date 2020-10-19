<template>
  <canvas ref="myChart" :width="width" :height="height"></canvas>
</template>

<script>
import Chart from 'chart.js';

export default {
  name: 'LineChart',
  props: {
    width: {
      type: Number,
      validator: value => value > 0
    },

    height: {
      type: Number,
      validator: value => value > 0
    },

    labels: Array,

    datasets: {
      type: Array,
      required: true
    },
    type: {
      type: String,
      default: 'Bar'
    },
    options: Object
  },
  data() {
    return {
      chart: null
    };
  },
  watch: {
    datasets(newDatasets) {
      this.chart.data.datasets = newDatasets;
      this.chart.update();
    }
  },
  mounted() {
    this.chart = new Chart(this.$refs.myChart, {
      type: this.type,
      data: {
        labels: this.labels,
        datasets: this.datasets
      },
      options: this.options
    });
  },
  beforeUnmount () {
    if (this.chart) {
      this.chart.destroy()
    }
  }
}
</script>
