<template>
  <!-- @TODO: 
          fix colors and spacing 
          fix scrollpanel
  -->
  <div class="main-wrapper">
    <div class="p-3">
      <div class="first-row flex flex-row">
        <div class="col-2 p-0">
          <QuickStat
            class="m-2"
            cardClass="orange-border"
            statCategory="Students Online"
            statNumber="24"
            iconClass="pi-users orange"
          />
        </div>
        <div class="col-2 p-0">
          <QuickStat
            class="m-2"
            cardClass="green-border"
            statCategory="Active Courses"
            statNumber="8"
            iconClass="pi-th-large green"
          />
        </div>
        <div class="col-2 p-0">
          <QuickStat
            class="m-2"
            cardClass="blue-border"
            statCategory="Courses"
            statNumber="112"
            iconClass="pi-book blue"
          />
        </div>
        <div class="col-2 p-0">
          <QuickStat
            class="m-2"
            cardClass="pink-border"
            statCategory="Completed Courses"
            statNumber="47"
            iconClass="pi-check-circle pink"
          />
        </div>
        <div class="col-4 p-0">
          <Schedule class="m-2" />
          <StudentStats class="mx-2 my-3" />
          <Announcements class="mx-2 my-3" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Announcements from '@/components/widgets/Announcements.vue';
import QuickStat from '@/components/widgets/QuickStat.vue';
import Schedule from '@/components/widgets/Schedule.vue';
import StudentStats from '@/components/widgets/StudentStats.vue';

export default {
  components: {
    Announcements,
    QuickStat,
    Schedule,
    StudentStats,
  },
};
</script>

<style></style>
