<template>
  <div class="container">
    <h2 class="text-center">Todo Application</h2>
    <hr>
    <AddSection :addNewTodo="addNewTodo" @add-todo="addNewTodo"/>
    <ListSection/>
  </div>
 
</template>

<script>
import AddSection from "@/components/AddSection.vue"
import ListSection from "@/components/ListSection.vue"
export default {
  name: 'App',
  components: {
    ListSection,
    AddSection
  },
  data() {
    return {
      provideData: {
        todoList: [
          {id:1,text:"Something todo #1"},
          {id:2,text:"Something todo #2"},
          {id:3,text:"Something todo #3"},
          {id:4,text:"Something todo #4"},
          {id:5,text:"Something todo #5"},
          {id:6,text:"Something todo #6"}
        ]
      }
    };
  },
  provide() {
    return {
      provideData: this.provideData,
      deleteItem: this.deleteItem
    };
  },
  methods: {
    deleteItem(todoItem) {
      console.log(todoItem);
      this.provideData.todoList = this.provideData.todoList.filter(t => t !== todoItem);
    },
    addNewTodo(todo) {
      this.provideData.todoList.push({
        id: new Date().getTime(),
        text: todo
      });
    }
  }
}
</script>



<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

