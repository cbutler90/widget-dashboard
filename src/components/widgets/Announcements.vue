<template>
  <WidgetContainer title="Announcements">
    <ScrollPanel class="w-full mb-3 pt-3" style="height: 382px">
      <AnnouncementCard />
    </ScrollPanel>
    <a href="#">View All Announcements</a>
  </WidgetContainer>
</template>

<script>
import AnnouncementCard from '@/components/widgets/AnnouncementCard.vue';
import WidgetContainer from '@/components/WidgetContainer.vue';

export default {
  components: {
    AnnouncementCard,
    WidgetContainer,
  },
};
</script>

<style></style>
