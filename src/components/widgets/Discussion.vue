<template>
  <WidgetContainer title="Discussion">
    <div class="grid pl-2 discussions relative">
      <ScrollPanel class="w-full discussion mb-3" style="height: 346px">
        <DiscussionCard />
      </ScrollPanel>
      <span class="fade"></span>
      <div class="w-full">
        <a href="#" class="text-sm">View All Discussions</a>
      </div>
    </div>
    </WidgetContainer>
</template>

<script>
  import DiscussionCard from './DiscussionCard.vue';
  import WidgetContainer from '../WidgetContainer.vue';

export default {
  components: {
    DiscussionCard,
    WidgetContainer,
  }
};
</script>

<style scoped>
  .fade {
      position: absolute;
      bottom: 29px;
      left: 0;
      display: block;
      width: 100%;
      height: 40px;
      z-index: 999;
      background-image: linear-gradient(360deg, #1d1e30 0%, #2b2d4600 100%);
  }
</style>
