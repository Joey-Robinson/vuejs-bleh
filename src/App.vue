<template>
  <main id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </main>
</template>

<script>
import Todos from "./components/todos"
import Header from "./components/header"
import AddTodo from "./components/todo.add"

export default {
  name: "App",
  components: {
    Header,
    AddTodo,
    Todos,
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Todo One",
          completed: false,
        },
        {
          id: 2,
          title: "Todo Two",
          completed: true,
        },
        {
          id: 3,
          title: "Todo Three",
          completed: false,
        },
      ],
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo]
    },
  },
}
</script>

<style>
*,
::before,
::after {
  box-sizing: border-box;
  padding: 0;
  margin: ;
}
body {
  background: #304457;
  color: white;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover {
  background: #666;
}
</style>
