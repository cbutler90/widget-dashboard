<template>
    <ul class="pt-3">
        <li
          v-for="announcement in announcements"
          :key="announcement.id"
          :class="announcement.color"
        >
          <i class="pi pi-circle-on"></i>
          <div class="event-content">
            <span class="event-title heather">{{ announcement.title }}</span>
            <span class="font-normal text-sm">{{
              announcement.description
            }}</span>
            <span class="time">{{ announcement.postedDateTime }}</span>
          </div>
        </li>
      </ul>
</template>

<script>
export default {
  data() {
    return {
      announcements: [
        {
          id: 1,
          color: 'green',
          title: 'New Course Available',
          description: 'Please review the new course prior to class',
          postedDateTime: '3 min ago',
        },
        {
          id: 2,
          color: 'blue',
          title: 'Due Date Changed',
          description: 'The due date has been adjusted for Course 1',
          postedDateTime: '12 min ago',
        },
        {
          id: 3,
          color: 'orange',
          title: 'Reminder',
          description: "Don't forget your course is due Friday",
          postedDateTime: '1:30 pm',
        },
        {
          id: 4,
          color: 'orange',
          title: 'Class Cancelled',
          description: 'Class will resume on Tuesday',
          postedDateTime: '09/10/2022',
        },
        {
          id: 5,
          color: 'green',
          title: 'New Discussion',
          description: 'New Discussion has been posted',
          postedDateTime: '09/01/2022',
        },
        {
          id: 6,
          color: 'green',
          title: 'New PDF Available',
          description: 'Please download the PDF uploaded for Course 1',
          postedDateTime: '08/31/2022',
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
  .annoucements {
  padding-right: 4px;
  ul {
    padding: 0;
    margin: 0;
    list-style: none;
    max-height: 372px;
    margin-bottom: 1em;

    > li {
      display: flex;
      margin-bottom: 16px;

      > i {
        font-size: 8px;
        margin-right: 10px;
        margin-top: 4px;
      }

      .event-content {
        span {
          display: block;
          margin-bottom: 4px;
          font-weight: 600;
          font-size: 12px;
          color: #8597ae;

          &.event-title {
            color: #d1e1f6;
          }

          &.time {
            font-size: 10px;
            font-weight: 400;
            color: #8597ae;
          }
        }
      }

      &.blue {
        > i {
          // color: #297FFF;
          color: #5465FF;
        }
      }
      &.green {
        > i {
          color: #6BD425;
        }
      }
      &.orange {
        > i {
          color: #FBB13C;
        }
      }
    }
  }
}
</style>
