<template>
<div @dblclick="$emit('toggle-reminder', id)" :class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>
        {{task.text}}
        <i @click="$emit('delete-task', id)" class="fas fa-times"></i>
    </h3>
    <p>{{task.day}}</p>
</div>
</template>

<script>
export default {
    name: 'Task',
    props: {
        task: Object,
    }
}
</script>

<style scope>
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
  border-radius:6px;
  /* animation-name: color;
  animation-duration: 1s;
  animation-iteration-count: 1; */
}

/* @keyframes color {
  0% {
    background-color: #e4e4e4;
  }
  50% {
    background-color: white;
  }
  100% {
    background-color: #e4e4e4;
  }
} */

.task:hover{
  background: white;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.task.reminder {
  animation-name: color;
  animation-duration: 1s;
  animation-iteration-count: 1;
  border-left: 3px solid #42b883;
}
@keyframes color {
  0% {
    background-color: #f4f4f4;
  }

  50% {
    background-color: #A0DBC1;
  }

  100% {
    background-color: #f4f4f4;
  }
}
</style>