<template>
  <WidgetContainer title="Discussion">
      <ScrollPanel class="w-full discussion py-3 mb-2" style="height: 346px">
        <DiscussionCard />
      </ScrollPanel>
      <a href="#" class="text-sm">View All Discussions</a>
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

<style></style>
