<template>
  <!-- @TODO:
          figure out filter on events data (start,end)
  -->
  <ul>
      <li v-for="event in filteredEvents" :key="event.id" :class="statusChecker(event)">
          <div class="schedule-header">
              <h6 class="text-lg letter-s-normal">{{ event.title }}</h6>
          </div>
          <div class="schedule-content flex justify-content-between align-items-center">
              <div class="flex flex-column">
                  <a href="#" v-if="event.cta">{{ event.cta }}</a>
                  <span class="participants" v-if="event.numOfParticipants">{{ event.numOfParticipants }} participants</span>
              </div>
              <span class="text-base time">{{ event.begin }} - {{ event.close }}</span>
          </div>
      </li>
  </ul>
</template>

<script>
export default {
  data() {
      return {
          events: [
            {
              id: 1,
              title: 'test',
              cta: 'Join Session',
              numOfParticipants: 4,
              start: '2022-09-09T16:00:00',
              end: '2022-09-10T16:00:00',
              begin: '12:00',
              close: '16:00',
            }
          ],
      };
  },
  methods: {
      statusChecker(event) {
          let now = new Date();
          let start = new Date(event.start);
          let status = start < now ? 'past' : 'upcoming';
          if (start.getUTCFullYear() == now.getUTCFullYear() && start.getUTCMonth() == now.getUTCMonth() && start.getUTCDate() == now.getUTCDate()) {
              status = 'today';
          }
          return status;
      },
  },
  computed: {
      filteredEvents() {
          return this.events.filter(event => this.statusChecker(event) !== 'past');
      },
  },
};
</script>

<style></style>
