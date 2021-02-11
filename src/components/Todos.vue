<template>
  <section class="todoapp">
    <header class="header">
      <h1>Todos</h1>
      <input
        type="text"
        class="new-todo"
        placeholder="Ajouter une tache"
        v-model="newTodo"
        @keyup.enter="addTodo"
      />
    </header>
    <div class="main">
      <ul class="todo-list">
        <li
          class="todo"
          v-for="todo in todos"
          :class="{ completed: todo.completed }"
          :key="todo.id"
        >
          <div class="view">
            <input type="checkbox" v-model="todo.completed" class="toggle" />
            <label> {{ todo.name }}</label>
          </div>
        </li>
      </ul>
    </div>
    <footer class="footer">
      <span class="todo-count"
        ><strong>{{ remaining }}</strong> Tâche(s) a faire</span>
      <ul class="filters">
        <li><a href="#" class="selected">Toutes</a></li>
        <li><a href="#">A faire</a></li>
        <li><a href="#">Faites</a></li>
      </ul>
    </footer>
  </section>
</template>
<script>
export default {
  data () {
    return {
      todos: [
        {
          name: 'Tache de test',
          completed: false
        }
      ],
      newTodo: ''
    }
  },
  methods: {
    addTodo () {
      this.todos.push({
        completed: false,

        name: this.newTodo
      })
      this.newTodo = ''
    }
  },
  computed: {
    remaining () {
      return this.todos.filter(todo => !todo.completed).length
    }
  }
}
</script>
<style src="./todos.css"></style>
