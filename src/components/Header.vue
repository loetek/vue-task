<template>
<header>
    <span v-bind:style="{ 'color': '#42b883' }">
        <i @mouseover="isHover = true" @mouseout="isHover = false" :class="isHover ? 'fab fa-vuejs fa-3x pulse' : 'fab fa-vuejs fa-3x'"></i>
    </span>
    <h1> {{title}}</h1>
    <Button btnColor='#42b883' btnText="Add Task"></Button>
</header>
</template>

<script>
import Button from './Button.vue'
export default {
    name: "Header",
    props: {
        title: String,
        isHover: Boolean,
    },
    components: { Button }
}
</script>

<style scoped>
    header{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
</style>


