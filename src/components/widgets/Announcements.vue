<template>
  <WidgetContainer title="Announcements">
    <div class="grid pl-3 annoucements relative">
      <ScrollPanel class="w-full mb-3" style="height: 382px">
        <AnnouncementCard />
      </ScrollPanel>
      <span class="fade"></span>
      <div class="w-full">
        <a href="#" class="text-sm">View All Announcements</a>
      </div>
    </div>
  </WidgetContainer>
</template>

<script>
import AnnouncementCard from './AnnouncementCard.vue';
import WidgetContainer from '../WidgetContainer.vue';

export default {
  components: {
    AnnouncementCard,
    WidgetContainer,
  },
};
</script>

<style scoped>
.fade {
      position: absolute;
      bottom: 35px;
      left: 0;
      display: block;
      width: 100%;
      height: 40px;
      z-index: 999;
      background-image: linear-gradient(360deg, #1d1e30 0%, #2b2d4600 100%);
  }
</style>
