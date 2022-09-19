<template>
  <div class="quick-stat-card border-round-md raisin-black-bg p-3" :class="cardClass">
    <div class="stat-content flex flex-row justify-content-between">
      <div class="stat flex-column">
        <h1 class="stat-category text-base casper mb-3">{{ statCategory }}</h1>
        <p class="stat-number text-4xl m-0 gainsboro">{{ statNumber }}</p>
      </div>
      <div class="stat-icon">
        <i class="text-xl pi" :class="iconClass"></i>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: [ 'cardClass', 'statCategory', 'statNumber', 'iconClass' ]
}
</script>

<style>
.quick-stat-card {
  border-left: 4px solid;
}
</style>