<template>
  <ul class="flex flex-wrap p-0 m-0 pr-3 mb-3" style="max-height: 175px">
    <li
      v-for="discussion in discussions"
      :key="discussion.id"
      class="col-12 p-0"
    >
      <div class="discussion-card mb-3">
        <div
          class="discussion-header flex align-items-center justify-content-between"
        >
          <a href="#">
            <h6 class="text-lg letter-s-normal font-normal mb-1 mt-2 gainsboro">
              {{ discussion.title }}
            </h6></a
          >
          <Button
            type="button"
            label="toggle"
            aria-haspopup="true"
            aria-controls="student_menu"
            class="cursor-pointer oslo-grey p-button-text px-1 align-self-start"
            @click="toggleMenu"
          >
            <i class="pi pi-ellipsis-h oslo-grey"></i>
          </Button>
          <Menu id="discussion_menu" ref="menu" :model="items" :popup="true" />
        </div>
        <p>{{ discussion.excerpt }}</p>
        <div
          class="discussion-content flex justify-content-between align-items-center"
        >
          <div class="flex flex-column">
            <span class="participants mb-1">{{ discussion.datePosted }}</span>
            <span class="comments font-normal" v-if="discussion.numOfComments"
              ><i class="pi pi-comment"></i>
              {{ discussion.numOfComments }} comments</span
            >
          </div>
          <AvatarGroup v-if="discussion.numOfParticipants">
            <Avatar
              image="/assets/demo/images/dashboard/avatar/af1.png"
              shape="circle"
              style="height: 2.25rem; width: 2.25rem"
            />
            <Avatar
              image="/assets/demo/images/dashboard/avatar/wm4.jpg"
              shape="circle"
              style="height: 2.25rem; width: 2.25rem"
            />
            <Avatar
              image="/assets/demo/images/dashboard/avatar/wf2.png"
              shape="circle"
              style="height: 2.25rem; width: 2.25rem"
            />
            <Avatar
              image="/assets/demo/images/dashboard/avatar/wf3.jpg"
              shape="circle"
              style="height: 2.25rem; width: 2.25rem"
            />
            <Avatar
              label="+9"
              shape="circle"
              style="height: 2.25rem; width: 2.25rem"
            />
          </AvatarGroup>
        </div>
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          label: 'View Discussion',
        },
        {
          label: 'Assign To',
        },
        {
          label: 'Edit',
        },
        {
          label: 'Delete',
        },
      ],
      discussions: [
        {
          id: 1,
          title: 'Discussion Board 1',
          excerpt: 'This week we really want to focus on working towards understanding the difference...',
          datePosted: '9/20/2022',
          numOfComments: 3,
          numOfParticipants: 13
        }
      ],
    };
  },
  methods: {
    toggleMenu(event) {
      this.$refs.menu.toggle(event);
    },
  },
};
</script>

<style></style>
