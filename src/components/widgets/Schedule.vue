<template>
  <WidgetContainer title="Today's Schedule">
    <div class="col-12 px-0 pb-0">
      <div class="append">
        <FullCalendar :events="events" :options="options" />
      </div>
    </div>
    <!-- <ScrollPanel
      class="w-full schedule"
      style="max-height: 185px; min-height: 94px"
    >
      <ScheduleCard />
    </ScrollPanel> -->
    <a href="#" class="text-sm">View Full Schedule</a>
  </WidgetContainer>
</template>

<script>
import '@fullcalendar/core/vdom';
import dayGridPlugin from '@fullcalendar/daygrid';
import timeGridPlugin from '@fullcalendar/timegrid';
import interactionPlugin from '@fullcalendar/interaction';
import ScheduleCard from './ScheduleCard.vue';
import WidgetContainer from '../WidgetContainer.vue';

export default {
  components: {
    ScheduleCard,
    WidgetContainer,
  },
  data() {
    return {
      eventDialog: false,
      clickedEvent: null,
      changedEvent: { title: '', start: null, end: '', allDay: null },
      options: {
        plugins: [dayGridPlugin, timeGridPlugin, interactionPlugin],
        defaultDate: '2021-07-01',
        headerToolbar: {
          left: 'prev',
          center: 'title',
          right: 'next',
        },
        editable: true,
        eventClick: (e) => {
          this.eventDialog = true;
          this.clickedEvent = e.event;
          this.changedEvent.title = this.clickedEvent.title;
          this.changedEvent.start = this.clickedEvent.start;
          this.changedEvent.end = this.clickedEvent.end;
        },
      },
      events: null,
    };
  },
  methods: {
    findIndexById(id) {
      let index = -1;
      for (let i = 0; i < this.events.length; i++) {
        if (this.events[i].id === id) {
          index = i;
          break;
        }
      }
      return index;
    },
    save() {
      this.eventDialog = false;
      this.clickedEvent.setProp('title', this.changedEvent.title);
      this.clickedEvent.setStart(this.changedEvent.start);
      this.clickedEvent.setEnd(this.changedEvent.end);
      this.clickedEvent.setAllDay(this.changedEvent.allDay);
      this.changedEvent = { title: '', start: null, end: '', allDay: null };
    },
    reset() {
      this.changedEvent.title = this.clickedEvent.title;
      this.changedEvent.start = this.clickedEvent.start;
      this.changedEvent.end = this.clickedEvent.end;
    },
  },
};
</script>

<style></style>
