<template>
  <ul class="todo-list">
    <AppTodoItem v-for="todo in todos" :key="todo.id" :todo="todo" />
  </ul>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import AppTodoItem from './AppTodoItem.vue';

export default defineComponent({
  components: {
    AppTodoItem,
  },

  data() {
    return {
      todos: [
        { id: 0, text: 'Learn the basics of Vue', completed: true },
        { id: 1, text: 'Learn the basics of TS', completed: false },
        { id: 2, text: 'Learn the basics of Nuxt', completed: false },
      ],
    };
  },
});
</script>
