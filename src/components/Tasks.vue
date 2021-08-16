<template>
  <div>
    <div v-for="task in tasks" :key="task.id">
        <Task @toggle-reminder="doToggle(task.id)" @delete-task="doDelete(task.id)" :task="task" />
    </div>
  </div>
</template>

<script>
import Task from './Task'

export default {
  name: "Tasks",
  props: {
    tasks: Array,
  },
  methods: {
      doDelete(id) {
          this.$emit('delete-task', id)
      }, 
      doToggle(id) {
          this.$emit('toggle-reminder', id)
      }
  },
  components: {
      Task
  }, 
};
</script>   