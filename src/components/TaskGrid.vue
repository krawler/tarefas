<template>
  <div class="tasks">
    <template v-if="tasks.length">
        <Task  @taskDeleted="$emit('taskDeleted', i)"
               @taskStateChanged="$emit('taskStateChanged', i)" 
               v-for="(task, i) in tasks"
               :key="task.name" 
               :task="task">
        </Task>
    </template>
    <p v-else class="no-task">Sua vida está em dia</p>
  </div>
</template>

<script>
import Task from './Task.vue'

export default {
  components: { Task },
    props: {
        tasks: { type: Array, required: true }
    }
}
</script>

<style>
    .tasks{
        display:flex;
        justify-content: center;
        flex-wrap:wrap;
    }

    .tasks .task{
        margin: 10px;
    }
</style>