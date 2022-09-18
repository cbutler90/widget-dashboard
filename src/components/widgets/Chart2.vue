<template>
  <WidgetContainer title="Courses Completed Each Month">
    <Chart
      type="line"
      :data="chart2"
      :options="chartOptions2"
      style="max-height: 330px"
    ></Chart>
  </WidgetContainer>
</template>

<script>
import WidgetContainer from '@/components/WidgetContainer.vue';

export default {
  components: {
    WidgetContainer,
  },
  data() {
    return {
      chart2: null,
      chartOptions2: {
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
      this.chart2 = this.getChart2();
    },
    getChart2() {
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
            label: 'Courses',
            data: [4, 6, 4, 7, 3, 5, 2],
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
