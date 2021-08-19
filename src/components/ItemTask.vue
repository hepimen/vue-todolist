<template>
  <div>
    <div class="form-check">
      <input
        class="form-check-input"
        type="checkbox"
        value=""
        id="defaultCheck1"
        onclick=""
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
};
</script>

<style scoped>
</style>