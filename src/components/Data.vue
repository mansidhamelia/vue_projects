<template>
    
    <div v-for="task in tasks" :key="task.id">
        <Task @toggle="$emit('toggle', task.id)" @delete-task="$emit('delete-task', task.id)" :task="task" />
    </div>
</template>

<script>

import Task from "./Task.vue";

export default {
    name: 'Tasks',
    props:{
        tasks: Array
    },
    components: {
        Task,
    },
    emits:['delete-task', 'toggle'],
}
</script>

