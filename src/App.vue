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
                <ItemTask v-bind:myTask="myTask" />
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
          id: 1,
          taskName: "Membersihkan Kamar",
          isDone: false,
        },
        {
          id: 2,
          taskName: "Memanggang Daging",
          isDone: false,
        },
        {
          id: 3,
          taskName: "Lari Pagi",
          isDone: false,
        },
        {
          id: 4,
          taskName: "Istirahat cukup",
          isDone: false,
        },
      ],
    };
  },
  components: {
    ItemTask,
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.header {
  background: rgba(125, 162, 197, 0.8);
}
.task .item {
  font-size: 20px;
}
.task-home {
  text-align: left;
}
.item-completed {
  color: rgb(8, 180, 8);
}
</style>
