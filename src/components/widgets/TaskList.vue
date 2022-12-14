<template>
  <WidgetContainer title="Task List">
    <div class="grid ml-0 flex-column">
        <ScrollPanel class="w-full mb-3" style="height: 424px;">
            <div class="p-inputgroup mt-3 mb-4" @keyup.enter="addTask" >
                <InputText class="task-input" placeholder="Add Task" :class="{ activated: newTask }" v-model="newTask" />
                <Button icon="pi pi-plus" class="p-button-success" :class="{ activated: newTask }" @click="addTask" />
            </div>
            <div v-if="pending.length > 0">
                <!-- <p class="status busy">You have {{ pending.length }} pending item<span v-if="pending.length > 1">s</span></p>
                <p class="status busy">You have {{ completed.length }} completed item<span v-if="completed.length > 1">s</span></p> -->
                <transition-group name="task" tag="ul" class="tasks pl-0">
                    <li class="field-checkbox relative block overflow-hidden" v-for="task in pending" :key="task.id">
                        <input class="task-checkbox" :id="`task-${task.id}`" v-model="task.done" v-bind:value="!task.done" type="checkbox" />
                        <label class="cursor-pointer absolute" :for="`task-${task.id}`"></label>
                        <span class="task-title">{{ task.title }}</span>
                        <span class="delete absolute h-full cursor-pointer" @click="deleteTask(task)"></span>
                    </li>
                </transition-group>
            </div>
            <transition name="slide-fade">
                <h6 class="text-base font-normal rhythm" v-if="!pending.length">You have no pending tasks</h6>
            </transition>
            <div v-if="completed.length > 0 && showComplete">
                <p class="pt-3">Completed Tasks: {{ completedPercentage }}</p>
                <transition-group name="task" tag="ul" class="tasks archived pl-0">
                    <li class="field-checkbox relative block overflow-hidden" v-for="task in completed" :key="task.id">
                        <input class="task-checkbox" :id="`task-${task.id}`" v-model="task.done" v-bind:value="!task.done" type="checkbox" checked />
                        <label class="cursor-pointer absolute" :for="`task-${task.id}`"></label>
                        <span class="task-title">{{ task.title }}</span>
                        <span class="delete absolute h-full cursor-pointer" @click="deleteTask(task)"></span>
                    </li>
                </transition-group>
            </div>
        </ScrollPanel>
        <div class="control-buttons flex align-items-center justify-content-between">
            <Button class="task-btn p-button-text p-0 text-sm" v-if="completed.length > 0" @click="toggleShowComplete">
                <span v-if="!showComplete">Show</span>
                <span v-else>Hide</span>
                &nbsp;Complete
            </Button>
            <Button class="task-btn p-button-text p-0 text-sm" v-if="tasks.length > 0" @click="clearAll">Clear All</Button>
        </div>
    </div>
  </WidgetContainer>
</template>

<script>
import WidgetContainer from '../WidgetContainer.vue';
// import TaskService from '../service/TaskService';
export default {
    data() {
        return {
            tasks: [],
            selectedTasks: [],
            newTask: "",
            showComplete: false,
            task: null,
        };
    },
    // taskService: null,
    // created() {
    //     this.taskService = new TaskService();
    // },
    mounted() {
        // this.taskService.getTasks().then(data => (this.tasks = data));
        this.getTasks();
    },
    watch: {
        tasks: {
            handler: function (recentList) {
                localStorage.setItem("tasks", JSON.stringify(recentList));
            },
            // look inside array
            deep: true,
        },
    },
    computed: {
        // get all outstanding tasks
        pending: function () {
            return this.tasks.filter(function (task) {
                return !task.done;
            });
        },
        // get all completed tasks
        completed: function () {
            return this.tasks.filter(function (task) {
                return task.done;
            });
        },
        // calculate percentage of completed tasks
        completedPercentage: function () {
            return Math.floor((this.completed.length / this.tasks.length) * 100) + "%";
        },
    },
    methods: {
        // get all tasks on load
        getTasks() {
            if (localStorage.getItem("tasks")) {
                this.tasks = JSON.parse(localStorage.getItem("tasks"));
            }
        },
        // add a new task
        addTask() {
            if (this.newTask) {
                this.tasks.unshift({
                    id: this.tasks.length + 1,
                    title: this.newTask,
                    done: false,
                });
            }
            // reset instance for a new task again
            this.newTask = "";
            // save task in localstorage
            return true;
        },
        // remove a task from the list
        deleteTask(task) {
            this.tasks.splice(this.tasks.indexOf(task), 1);
        },
        // toggleTaskComplete(event, task) {
        //     // let foundTask = this.tasks.find(t=>t.id===task.id);
        //     task.done = !task.done;
        // },
        // be able to toggle to show the completed items
        toggleShowComplete() {
            this.showComplete = !this.showComplete;
        },
        // clear all tasks
        clearAll() {
            this.tasks = [];
        },
    },
    components: { WidgetContainer }
};
</script>

<style lang="scss" scoped>
.p-button.p-button-text {
  color: #33CCFF !important;
  &:enabled:hover {
      background: transparent;
      color: #008AB8 !important;
      transition: color 200ms linear !important;
  }
}

.task-input {
  background-color: #0c0d1c !important;
  border-top-right-radius: 0px !important;
  border-bottom-right-radius: 0px !important;
  border: 1px solid #414469 !important;
  border-right: none !important;
}

ul.tasks {
  li {
      background: #2b2d46;
      list-style-type: none;
      margin: 10px 0;
      border-radius: 5px;
      padding: 12px 50px;
      color: #acbacc;
      .delete {
          top: 50%;
          right: 0;
          transform: translateY(-50%);
          opacity: 0;
          width: 0;
          background-color: #FC440F;
          color: #fff;
          transition: all ease-in 0.25s;
          &:after {
              position: absolute;
              content: '';
              width: 20px;
              height: 20px;
              top: 50%;
              left: 50%;
              background-image: url('/src/assets/img/icons/trashcan-white.svg');
              background-repeat: no-repeat;
              background-position: center;
              background-size: contain;
              transform: translate(-50%, -50%) scale(0.5);
              transition: all ease-in 0.25s;
          }
      }
      &:hover {
          .delete {
              width: 44px;
              opacity: 1;
              &:after {
                  transform: translate(-50%, -50%) scale(1);
              }
          }
      }
      .task-checkbox {
          position: absolute;
          opacity: 0;
          display: none;
          + label {
              left: 10px;
              top: 50%;
              transform: translateY(-50%);
              width: 20px;
              height: 20px;
              border-radius: 2px;
              border: 1px solid #00bfff;
              background-color: transparent;
          }
          &:checked {
              + label {
                  background: #00bfff;
                  &:after {
                      display: block;
                      position: absolute;
                      content: '';
                      top: 30%;
                      left: 50%;
                      height: 3px;
                      width: 6px;
                      border: solid #fff;
                      border-width: 0 0 2px 2px;
                      transform-origin: center center;
                      transform: rotate(-45deg) translate(-50%, -50%);
                  }
              }
              ~ .task-title {
                  color: #acbacc;
                  text-decoration: line-through;
              }
          }
      }
  }
  .archived li {
      background: black !important;
  }
}

.task-enter-active,
.task-leave-active {
  transition: opacity ease 0.25s, transform ease-in-out 0.3s;
  transform-origin: left center;
}

.task-enter,
.task-leave-to {
  opacity: 0;
  transform: translateX(100%);
}

.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: all 0.3s ease;
}

.slide-fade-enter,
.slide-fade-leave-to {
  transform: scale(1.1);
  opacity: 0;
}
</style>
