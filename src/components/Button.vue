<template>
    <AddTask ref='modal'></AddTask>
    <button @click="onClick()" backgroundColor={{bntColor}}>{{btnText}}</button>
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
