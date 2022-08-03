<template>
<div>
<Task :key="task.id" v-for="task in tasks" :task="task"></Task>
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
    }
}
</script>

