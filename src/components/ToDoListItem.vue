<template>
  <li class="todo-list-item">
    <span @click="updateValue(!value)">
      [ <span v-if="value">X</span> ]
    </span>
    <b>{{title}}</b>
    <div>
      <label>{{subtitle}}</label>
    </div>
  </li>
</template>

<script>
export default {
  name: "ToDoListItem",
  props: ["title", "subtitle", "value"],
  methods: {
    updateValue: function (value) {
      /*I added this to keep updated the v-model. 
      It does not interfere with the todo-list component.*/
      this.$emit("input",value);
    },
  },
};
</script>

<style scoped>
.todo-list-item{
  margin-top: 1rem;
}
</style>

