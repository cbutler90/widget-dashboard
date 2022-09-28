<template>
  <ul class="flex flex-wrap p-0 m-0 mb-3 pt-3" style="max-height: 175px">
    <li
      v-for="discussion in discussions"
      :key="discussion.id"
      class="col-12 p-0"
    >
      <div class="discussion-card mb-3 border-round-md py-2 px-3 cursor-pointer">
        <div
          class="discussion-header flex align-items-center justify-content-between"
        >
          <a href="#">
            <h6 class="text-base font-normal mb-1 mt-2 casper">
              {{ discussion.title }}
            </h6></a
          >
          <Button
            style="margin-right: -0.35rem"
            type="button"
            aria-haspopup="true"
            aria-controls="student_menu" icon="pi pi-ellipsis-v"
            @click="toggleMenu"
          />
          <Menu id="discussion_menu" ref="menu" :model="items" :popup="true" />
        </div>
        <p class="discussion-excerpt mt-0 shadow-blue text-sm">{{ discussion.excerpt }}</p>
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
          <!-- server isn't recognizing this, looking for src, will have to rebuild as our own -->
          <!-- <AvatarGroup v-if="discussion.numOfParticipants">
            <Avatar
              image="/src/assets/img/avatars/guy1.png"
              shape="circle"
              style="height: 2.25rem; width: 2.25rem"
            />
            <Avatar
              image="/src/assets/img/avatars/girl1.png"
              shape="circle"
              style="height: 2.25rem; width: 2.25rem"
            />
            <Avatar
              image="/src/assets/img/avatars/girl2.png"
              shape="circle"
              style="height: 2.25rem; width: 2.25rem"
            />
            <Avatar
              image="/src/assets/img/avatars/girl3.png"
              shape="circle"
              style="height: 2.25rem; width: 2.25rem"
            />
            <Avatar
              label="+9"
              shape="circle"
              style="height: 2.25rem; width: 2.25rem; background: #3d4067;"
            />
          </AvatarGroup> -->
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
        },
        {
          id: 2,
          title: 'Discussion Board 2',
          excerpt: 'This week we really want to focus on working towards understanding the difference...',
          datePosted: '9/20/2022',
          numOfComments: 3,
          numOfParticipants: 13
        },
        {
          id: 3,
          title: 'Discussion Board 3',
          excerpt: 'This week we really want to focus on working towards understanding the difference...',
          datePosted: '9/20/2022',
          numOfComments: 3,
          numOfParticipants: 13
        },
        {
          id: 4,
          title: 'Discussion Board 4',
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

<style lang="scss">
  .discussion-card {
    background-color: #2b2d46;
    border-left: 5px solid #613DC1;
    .participants, .comments {
      color: #8597ae9e;
    }
    &:hover, &:focus {
      background-color: #31334f;
      transition: background-color 200ms linear;
      h6.casper {
        color: lighten(#acbacc, 10%);
        transition: color 200ms linear;
      }
    }
  }
</style>
