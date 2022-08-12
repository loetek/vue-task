<template>
    <AddTask @add-task="$emit('add-task', newTask)" ref='modal'></AddTask>
    <button @click="onClick()" :style="{ background: btnColor }" class="btn" >{{btnText}}</button>
</template>

<script>
import AddTask from './AddTask.vue'
export default {
    name: "Button",
    props: {
        btnText: String,
        btnColor: String,
    },
    methods: {
        onClick() {
      this.$refs.modal.show() //executing the show method for the modal.
    }
        },
    components: { AddTask }
}
</script>

<style scoped>

</style>
