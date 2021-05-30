<template>
  <Task
    v-for="task in tasks"
    :key="task.id"
    :task="task"
    @delete-task="$emit('delete-task', task.id)"
    @toggle-reminder="$emit('toggle-reminder', task.id)"
  />
</template>

<script>
import Task from "./Task";

export default {
  name: "Tasks",
  props: {
    tasks: Array,
  },
  components: {
    Task,
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>