<template>
  <div id="app">
    <div class="container">
      <div class="row header mb-5 p-3">
        <div class="col-lg-12">
          <h2>What i do today</h2>
        </div>
      </div>
      <div class="row content">
        <div class="col-md-4">
          <div class="task-home">
            <div class="row">
              <div
                v-for="myTask in task"
                v-bind:key="myTask.id"
                class="task mb-3"
              >
                <ItemTask v-bind:myTask="myTask" @confirmTrue="confirmTrue" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css";
import ItemTask from "./components/ItemTask.vue";

export default {
  name: "App",
  data: function () {
    return {
      task: [
        {
          id: 0,
          taskName: "Membersihkan Kamar",
          isDone: false,
        },
        {
          id: 1,
          taskName: "Memanggang Daging",
          isDone: false,
        },
        {
          id: 2,
          taskName: "Lari Pagi",
          isDone: false,
        },
        {
          id: 3,
          taskName: "Istirahat cukup",
          isDone: false,
        },
      ],
    };
  },
  components: {
    ItemTask,
  },
  methods: {
    confirmTrue(id) {
      this.task[id].isDone = !this.task[id].isDone;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.header {
  background: #c0392b;
  color: #fff;
}
.task .item {
  font-size: 20px;
}
.task-home {
  text-align: left;
}
</style>
