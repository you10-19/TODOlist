<template>
  <div>
    <div>ToDoList</div>
    <div v-for="item in items" :key="item.name">
      <div class="item">
        <div class="name">タスク名: {{ item.name }}</div>
        <div class="state">状態:{{ item.state }} </div>
        <div class="item" :class="{finish: item.state === `未完`}"></div>
      </div>
    </div>
    <div>
      <label>
        タスク名
        <input type="text" v-model="newItemName">
      </label>
      <label>
        状態
        <input type="text" v-model="newItemState">
      </label>
      <button @click="addItem">add</button>
    </div>
  </div>
</template>

<style>
.finish {
  color: red;
}
</style>

<script>
export default {
  name: "ToDoList",
  data() {
    return {
      items: [
        {name: 'たまごを買う', state: `未完`},
        {name: 'りんごを買う', state: `完了済み`}],
      newItemName: "",
      newItemState: ""
    };
  },
  methods: {
    addItem() {
      this.items.push({ name: this.newItemName, state: this.newItemState });
    }
  }
};
</script>

