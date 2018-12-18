<template>
  <label class="question">
    <select @change="$emit('update', $event.target.value*1)" class="rounded font-weight-bold p-1">
      <option v-for="(option, key) of options" :value="key" :key="key">{{option}}</option>
    </select>
    <slot></slot>
    <span class="pl-1">{{description}}</span>
  </label>
</template>

<script>
module.exports = {
  props: ["description"],
  data: function() {
    return {
      options: ["請選擇", "◯", "╳"]
    };
  },
  created() {
    this.$emit("update", 0);
  }
};
</script>

<style scoped>
.rounded {
  text-align: center;
  text-align-last: center;
}
</style>