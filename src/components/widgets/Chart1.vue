<template>
  <WidgetContainer title="Student Pass Rate Per Month">
    <Chart
      type="line"
      :data="chart1"
      :options="chartOptions1"
      style="max-height: 330px"
    ></Chart>
  </WidgetContainer>
</template>

<script>
import WidgetContainer from '../WidgetContainer.vue';

export default {
  components: {
    WidgetContainer,
  },
  data() {
    return {
      chart1: null,
      chartOptions1: {
        plugins: {
          legend: {
            display: false,
          },
        },
        maintainAspectRatio: false,
        hoverMode: 'index',
        scales: {
          x: {
            display: true,
            grid: {
              color: 'rgba(255, 255, 255, 0.1)',
            },
            ticks: {
              color: '#BFC2C6',
            },
          },
          y: {
            display: true,
            grid: {
              color: 'rgba(255, 255, 255, 0.1)',
              borderDash: [5, 10],
            },
            ticks: {
              color: '#BFC2C6',
              min: 0,
              stepSize: 5,
            },
          },
        },
      },
    };
  },
  mounted() {
    this.refreshChart();
  },
  methods: {
    refreshChart() {
      this.chart1 = this.getChart1();
    },
    getChart1() {
      const borderColor =
        getComputedStyle(document.body).getPropertyValue('--primary-color') ||
        '#2c84d8';
      const backgroundColor =
        getComputedStyle(document.body).getPropertyValue(
          '--primary-lighter-color'
        ) || '#2c84d8';
      return {
        labels: ['JAN', 'FEB', 'MAR', 'APR', 'MAY', 'JUN', 'JUL'],
        datasets: [
          {
            label: 'Students',
            data: [4, 6, 8, 10, 11, 13, 20],
            borderColor: [borderColor],
            borderWidth: 4,
            fill: true,
            tension: 0.4,
            backgroundColor: [backgroundColor],
          },
        ],
      };
    },
  },
};
</script>

<style></style>
