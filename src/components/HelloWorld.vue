<template>
  <div>
    <h1>{{ msg }}</h1>
    <counter/>
    <to-do-list/>
  </div>
</template>

<script>
import Counter from "./Counter.vue";
import ToDoList from "./ToDoList.vue";

export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  components: {
    Counter,
    ToDoList
  }
};
</script>