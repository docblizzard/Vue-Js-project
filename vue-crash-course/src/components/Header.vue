<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      v-show="homePage"
      @btn-click="$emit('toggle-add-task')"
      :text="showAddTask ? 'Close' : 'Add Task'"
      :color="showAddTask ? 'red' : 'green'"
    ></Button>
  </header>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "Header-component",
  components: {
    Button,
  },
  props: {
    title: {
      type: String,
      default: "Default title",
    },
    showAddTask: Boolean,
  },
  computed: {
    homePage() {
      if (this.$route.path === "/") {
        return true;
      } else {
        console.log(this.$route.path);
        return false;
      }
    },
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>