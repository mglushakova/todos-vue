<template>
  <ul class="todo-list">
    <AppTodoItem
      v-for="todo in todos"
      :key="todo.id"
      :todo="todo"
      @toggle-todo="toggleTodo"
    />
  </ul>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import AppTodoItem from './AppTodoItem.vue';
import { Todo } from '@/types/Todo';

interface State {
  todos: Todo[];
}

export default defineComponent({
  components: {
    AppTodoItem,
  },

  data(): State {
    return {
      todos: [
        { id: 0, text: 'Learn the basics of Vue', completed: true },
        { id: 1, text: 'Learn the basics of TS', completed: false },
        { id: 2, text: 'Learn the basics of Nuxt', completed: false },
      ],
    };
  },
  methods: {
    toggleTodo(id: number) {
      const targetTodo = this.todos.find((todo: Todo) => todo.id === id);

      if (targetTodo) {
        targetTodo.completed = !targetTodo.completed;
      }
    },
  },
});
</script>
