<template>
<div>
<Task @delete-task="$emit('delete-task', task.id)" :key="task.id" v-for="task in tasks" :task="task"></Task>
</div>
</template>

<script>
import Task from './Task.vue'
export default{
    name: 'Tasks',
    props:{
        tasks : Array,
    },
    components:{
        Task,
    },
    emits: ['delete-task']
}
</script>

