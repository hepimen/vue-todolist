<template>
  <div>
    <div class="form-check">
      <input
        class="form-check-input"
        type="checkbox"
        value=":value"
        id="defaultCheck1"
        v-on:click="confirmTrue"
      />
      <label
        class="form-check-label item"
        for="defaultCheck1"
        v-bind:class="{ 'item-completed': myTask.isDone }"
      >
        {{ myTask.taskName }}
      </label>
    </div>
  </div>
</template>

<script>
export default {
  name: "myTask",
  props: ["myTask"],
  methods: {
    confirmTrue() {
      console.info("bisa");
      this.mytask.isDone = true;
    },
  },
};
</script>

<style>
.item-completed {
  color: rgb(8, 180, 8);
}
</style>