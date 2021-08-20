<template>
  <div class="item-task">
    <div class="form-check">
      <input
        class="form-check-input"
        type="checkbox"
        value=":value"
        id="defaultCheck1"
        v-on:click="$emit('confirmTrue', myTask.id)"
      />
      <label
        class="form-check-label item"
        for="defaultCheck1"
        v-bind:class="{ 'item-completed': myTask.isDone }"
      >
        {{ myTask.taskName }}
      </label>
    </div>
    <!-- <button v-on:click="$emit('add-user')">Submit</button> -->
  </div>
</template>

<script>
export default {
  name: "myTask",
  props: ["myTask"],
};
</script>

<style>
.item-completed {
  color: #e74c3c;
}
</style>