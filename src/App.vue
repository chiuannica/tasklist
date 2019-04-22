<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';

export default {
  name: 'app',
  components: {
    Header,
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Feed the dog",
          completed: false
        },
        {
          id: 2,
          title: "Vacuum",
          completed: false
        },
        {
          id: 3,
          title: "Do homework",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    }
  }
}
</script>

<style>
@font-face {
  font-family: 'Montserrat';

  src: url("Montserrat-Light.ttf");
}
html{
  background-image: url("bg.png");
	background-position: top;
}
#app {
  font-family: 'Montserrat', sans-serif;
  -webkit-text-size-adjust: 100%;
  -ms-text-size-adjust: 100%;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  line-height: 1.4;
  color: #2c3e50;
  margin-top: 60px;
}
button{
  font-family: 'Montserrat';
}
</style>
