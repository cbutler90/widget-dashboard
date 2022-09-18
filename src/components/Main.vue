<template>
  <!-- @TODO: 
          fix colors on quick stat cards
  -->
  <div class="main-wrapper">
    <div class="p-3">
      <div class="first-row flex flex-row">
        <div class="col-2">
          <QuickStat cardClass="orange-border" statCategory="Students Online" statNumber="24" iconClass="pi-users orange" />
        </div>
        <div class="col-2">
          <QuickStat cardClass="green-border" statCategory="Active Courses" statNumber="8" iconClass="pi-th-large green" />
        </div>
        <div class="col-2">
          <QuickStat cardClass="blue-border" statCategory="Courses" statNumber="112" iconClass="pi-book blue" />
        </div>
        <div class="col-2">
          <QuickStat cardClass="pink-border" statCategory="Completed Courses" statNumber="47" iconClass="pi-check-circle pink" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuickStat from '@/components/widgets/QuickStat.vue'

export default {
  components: {
    QuickStat
  }
}
</script>

<style>

</style>