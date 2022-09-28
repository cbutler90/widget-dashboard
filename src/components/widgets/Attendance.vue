<template>
  <WidgetContainer title="Attendance This Month">
    <Chart type="doughnut" :data="chartData" :options="darkOptions" style="margin: 1rem 0rem; aspect-ratio: 2" />
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
      chartData: {
        labels: ['Present', 'Unexcused Absence', 'Excused Absence'],
        datasets: [
          {
            data: [11, 1, 3],
            backgroundColor: ['#FF47DA', '#03B5AA', '#FBB13C'],
            hoverBackgroundColor: ['#FF47DA', '#03B5AA', '#FBB13C'],
            borderColor: ['#8F0072', '#02645E', '#A06403'],
            borderWidth: 5,
            hoverBorderColor: ['#8F0072', '#02645E', '#A06403'],
            hoverBorderWidth: 8
          },
        ],
      },
      darkOptions: {
        maintainAspectRatio : false,
        plugins: {
          legend: {
            display: true,
            position: 'bottom',
            labels: {
              color: '#acbacc',
              padding: 20,
            },
          },
        },
      },
    };
  },
};
</script>
