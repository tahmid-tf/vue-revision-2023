<template>
  <div>
    <div class="container">
      <Header title="Task Tracker" @showAddTask="showAddTask"></Header>
      <AddTask @add-task="addTask"></AddTask>
      <Tasks
        :tasks="tasks"
        @delete-task="deleteTask"
        @toggle-reminder="toggleReminder"
      />
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";
import AddTask from "./components/AddTask.vue";

export default {
  components: {
    Header,
    Tasks,
    AddTask,
  },

  data() {
    return {
      tasks: [],
      gg: [],
    };
  },

  methods: {
    showAddTask(data) {
      console.log(data);
    },

    addTask(data) {
      this.tasks.push(data);
    },

    deleteTask(id) {
      this.tasks.splice(id - 1, 1);
    },

    toggleReminder(id) {
      this.tasks.forEach((el) => {
        if (el.id == id) {
          el.reminder = !el.reminder;
        }
      });
    },
  },

  created() {
    this.tasks = [
      {
        id: 1,
        text: "Doctors Appoinment",
        day: "March 1st at 2:30pm",
        reminder: true,
      },

      {
        id: 2,
        text: "Meeting at school",
        day: "April 2nd at 2:30pm",
        reminder: true,
      },

      {
        id: 3,
        text: "Food Shopping",
        day: "May 3rd at 2:30pm",
        reminder: false,
      },
    ];
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "Poppins", sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
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
