<template>
  <div>
    <div class="custom-control custom-radio" v-for="(text, key) of description" :key="key">
      <input type="radio" :name="name" :value="key" class="custom-control-input" :id="name+key" @input="$emit('update', $event.target.value*1)">
      <label class="custom-control-label" :for="name+key" v-if="key>0">
        ({{key}}) {{text}}
      </label>
      <div v-if="key==0" style="margin-left: -1.5rem;margin-bottom: 1rem;">{{text}}</div>
    </div>
  </div>
</template>

<script>
module.exports = {
  props: ["description"],
  data: function() {
    return {
      name: Math.random().toString(36).substring(2)
    };
  },
  created() {
    this.$emit("update", 0);
  }
};
</script>

<style scoped>
</style>