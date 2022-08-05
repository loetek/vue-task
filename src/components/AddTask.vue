<template>
<Teleport to="body">
<Transition name="slide-fade">
    <div v-if="showModal" class="modal">
    <div id="modal" >
        <div class="modal-header">
            <p>Hello from the modal!</p>
        <i @click="hide" class="fas fa-times modal-x" ></i>
    </div>
    <form @submit="onSubmit" class="add-form">
    <div class="form-control">
        <label>Task</label>
      <input type="text" v-model="text" name="text" placeholder="Add Task" />
    </div>
    <div class="form-control">
        <label>Day & Time</label>
      <input
        type="text"
        v-model="day"
        name="day"
        placeholder="Add Day & Time"
      />
    </div>
    <div class="form-control form-control-check">
        <label>Set Reminder</label>
      <input type="checkbox" v-model="reminder" name="reminder" />
    </div>

    <input @click="hide" type="submit" value="Save Task" class="btn btn-block" />
  </form>
    </div>
  </div>
  </Transition>
</Teleport>
</template>

<script>
export default {
   data() {
     return {
      showModal: false
     }
   },
   methods: {
     show() {
      this.showModal = true
     },
     hide(){
      this.showModal = false
     }
   }
 }
</script>

<style scoped>
.modal-x{
    color: black;
    padding-top: 3px;
    cursor: pointer;
}
.modal-header{
    display: flex;
    justify-content: space-between;
}
.modal {
  position: fixed;
  z-index: 999;
  top: 20%;
  left: 50%;
  width: 400px;
  margin-left: -150px;
  background-color: #f4f4f4;
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top: 30px;
  padding-bottom: 30px;
  border-radius: 6px;
  border-style: solid;
  border-color: black;

}
.add-form {
  margin-bottom: 20px;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.form-control-check label {
  flex: 1;
}
.form-control-check input {
  flex: 2;
  height: 20px;
}

.btn{
    background: #42b883;
}

/*
  Enter and leave animations can use different
  durations and timing functions.
*/
.slide-fade-enter-active {
  transition: all 0.8s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(20px);
  opacity: 0;
}
</style>