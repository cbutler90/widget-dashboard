<template>
  <WidgetContainer title="Announcements">
    <div class="grid pl-3 annoucements">
      <ScrollPanel class="w-full mb-3 pt-3" style="height: 382px">
        <AnnouncementCard />
      </ScrollPanel>
      <a href="#" class="capri">View All Announcements</a>
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

<style></style>
