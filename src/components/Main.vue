<template>
  <!-- @TODO: 
          fix colors and spacing
  -->
  <div class="main-wrapper pb-3">
    <div class="p-3">
      <div class="flex flex-column xl-2:flex-row">
        <div class="col-12 xl-2:col-8 p-0">
          <div class="flex flex-wrap lg:flex-row">
            <div class="col-12 md:col-6 lg:col-3 p-0">
              <QuickStat
                class="mx-2 my-2 lg:mt-2"
                cardClass="marigold-border"
                statCategory="Students Online"
                statNumber="24"
                iconClass="pi-users marigold"
              />
            </div>
            <div class="col-12 md:col-6 lg:col-3 p-0">
              <QuickStat
                class="mx-2 my-2 lg:mt-2"
                cardClass="lime-green-border"
                statCategory="Active Courses"
                statNumber="8"
                iconClass="pi-th-large lime-green"
              />
            </div>
            <div class="col-12 md:col-6 lg:col-3 p-0">
              <QuickStat
                class="mx-2 my-2 lg:mt-2"
                cardClass="neon-blue-border"
                statCategory="Courses"
                statNumber="112"
                iconClass="pi-book neon-blue"
              />
            </div>
            <div class="col-12 md:col-6 lg:col-3 p-0">
              <QuickStat
                class="mx-2 my-2 lg:mt-2"
                cardClass="orchid-border"
                statCategory="Completed Courses"
                statNumber="47"
                iconClass="pi-check-circle orchid"
              />
            </div>
          </div>
          <div class="flex flex-wrap lg:flex-row">
            <div class="col-12 md:col-5 p-0">
              <TaskList class="mx-2 mb-3 mt-2" />
              <Messages class="mx-2 my-3" />
              <Discussion class="mx-2 my-3" />
            </div>
            <div class="col-12 md:col-7 p-0">
              <FileUploadW class="mx-2 mb-3 mt-2" />
              <Chart1 class="mx-2 mb-3" />
              <Chart2 class="mx-2 mb-3" />
              <Chart3 class="mx-2 mb-3" />
              <Attendance class="mx-2 mb-3" />
            </div>
          </div>
          <!-- <div class="flex flex-row">
            <div class="col-5">
              <TaskList class="mx-2 my-3" />
            </div>
            <div class="col-7">
              <Messages class="mx-2 my-3" />
            </div>
          </div> -->
        </div>
        <div class="col-12 xl-2:col-4 p-0">
          <div class="flex flex-wrap">
            <div class="col-12 lg:col-6 xl-2:col-12 p-0">
              <Schedule class="m-2" />
            </div>
            <div class="col-12 lg:col-6 xl-2:col-12 p-0">
              <StudentStats class="m-2" />
            </div>
            <div class="col-12 lg:col-6 xl-2:col-12 p-0">
              <Announcements class="m-2" />
            </div>
          </div>
        </div>
      </div>
      <!-- <div class="flex flex-row">
        <div class="col-4 p-0">
          <Chart1 class="mx-2 mb-3" />
        </div>
        <div class="col-4 p-0">
          <Chart2 class="mx-2 mb-3" />
        </div>
        <div class="col-4 p-0">
          <Chart3 class="mx-2 mb-3" />
        </div>
      </div> -->
    </div>
  </div>
</template>

<script>
import Announcements from '@/components/widgets/Announcements.vue';
import Attendance from '@/components/widgets/Attendance.vue';
import Chart1 from '@/components/widgets/Chart1.vue';
import Chart2 from '@/components/widgets/Chart2.vue';
import Chart3 from '@/components/widgets/Chart3.vue';
import Discussion from '@/components/widgets/Discussion.vue';
import FileUploadW from '@/components/widgets/FileUploadW.vue';
import Messages from '@/components/widgets/Messages.vue';
import QuickStat from '@/components/widgets/QuickStat.vue';
import Schedule from '@/components/widgets/Schedule.vue';
import StudentStats from '@/components/widgets/StudentStats.vue';
import TaskList from '@/components/widgets/TaskList.vue';

export default {
  components: {
    Announcements,
    Attendance,
    Chart1,
    Chart2,
    Chart3,
    Discussion,
    FileUploadW,
    Messages,
    QuickStat,
    Schedule,
    StudentStats,
    TaskList
  },
};
</script>

<style></style>
