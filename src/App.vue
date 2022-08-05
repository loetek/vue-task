<template>
<div class="container">
  <Header title=" Task Tracker"></Header>
  <Tasks @delete-task="deleteTask" @toggle-reminder="toggleReminder" :tasks="tasks"></Tasks>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Tasks from './components/Tasks.vue'
// import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    // Footer,
    Tasks,
  },
  data(){
    return{
      tasks: []
    }
  },
  methods:{
    deleteTask(id){
      if(confirm('Are you sure???')){
        this.tasks = this.tasks.filter((task) => task.id !== id )
      }
    },
    toggleReminder(id){
      //Object literal spread operator. Toggling the value based based on the key to the matching id.
      this.tasks = this.tasks.map((task) => task.id === id ? {...task, reminder : !task.reminder} : task )
    }
  },
  created(){
    this.tasks = [
      {
        id: 1,
        text: 'Doc appt',
        day: 'March 1st',
        reminder: true
      },
         {
        id: 2,
        text: 'Dentist appt',
        day: 'March 5',
        reminder: false
      },
         {
        id: 3,
        text: 'Party',
        day: 'March 9th',
        reminder: true
      },
    ]
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid black;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
