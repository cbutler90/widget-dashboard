<template>
  <!-- @TODO:
          figure out filter on events data (start,end)
  -->
  <ul>
      <li v-for="event in filteredEvents" :key="event.id" :class="statusChecker(event)">
          <div class="schedule-header">
              <h6 class="text-lg">{{ event.title }}</h6>
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
              title: 'All Day Event',
              cta: 'Join Session',
              start: '2022-09-27',
              numOfParticipants: 4,
              begin: '12:00',
              close: '16:00',
            },
            {
              id: 2,
              title: 'Long Event',
              cta: 'Join Session',
              start: '2022-09-27',
              end: '2022-09-28',
              numOfParticipants: 12,
              begin: '12:00',
              close: '16:00',
            },
            {
              id: 3,
              title: 'Repeating Event',
              cta: 'Join Session',
              start: '2022-09-09T16:00:00',
              numOfParticipants: 11,
              begin: '12:00',
              close: '16:00',
            },
            {
              id: 4,
              title: 'Repeating Event',
              cta: 'Join Session',
              start: '2022-09-16T16:00:00',
              numOfParticipants: 11,
              begin: '12:00',
              close: '16:00',
            },
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
