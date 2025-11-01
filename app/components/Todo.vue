<script lang="ts" setup>
const todo = ref("");
const todos = ref<{ id: number; text: string }[]>([]);

const addTodo = () => {
  if (todo.value.trim() === "") return;
  todos.value.push({ id: Date.now(), text: todo.value });
  todo.value = "";
};

const deleteTodo = (id: number) => {
  todos.value = todos.value.filter((t) => t.id !== id);
};
</script>

<template>
  <UCard class="w-1/4">
    <template #header>
      <p>TodoApp</p>
    </template>
    <UInput v-model="todo" />
    <UButton @click="addTodo">add</UButton>
    <ul>
      <li v-for="todo in todos" :key="todo.id" class="flex justify-between">
        {{ todo.text }}
        <UButton size="sm" @click="deleteTodo(todo.id)">delete</UButton>
      </li>
    </ul>
  </UCard>
</template>
