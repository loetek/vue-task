<template>
<header>
    <!-- <span v-bind:style="{ 'color': '#42b883' }">
        <i @mouseover="isHover = true" @mouseout="isHover = false" :class="isHover ? 'fab fa-vuejs fa-3x pulse' : 'fab fa-vuejs fa-3x'"></i>
    </span> -->
    <img
        v-bind:src="picture"
        :alt="`${firstName}`"
        :class="gender"
      />
    <h2> hello Dave</h2>
    <Button btnColor='#42b883' btnText="Add Task"></Button>
    <AddTask @add-task="$emit('add-task', newTask)"></AddTask>
</header>
</template>

<script>
import Button from './Button.vue'
import AddTask from './AddTask.vue';

export default {
    name: "Header",
    props: {
        title: String,
        isHover: Boolean,
    },
    components: { Button, AddTask },
    data() {
    return {
      firstName: 'John',
      picture: 'data:image/jpeg;base64,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',
    }
  },
}
</script>

<style scoped>
    header{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    img {
        border-radius: 50%;
        border: 3px #333 solid;
        margin-bottom: 1rem;
        border-color: #42b883;
        background-color:#42b883;
        height: 100px;
        width: 100px;
        }
</style>


