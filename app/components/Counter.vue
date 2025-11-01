<script lang="ts" setup>
const counter = ref(0);

const inclease = () => {
  counter.value += 1;
};

const declease = () => {
  if (counter.value === 0) return;
  counter.value -= 1;
};

const reset = () => {
  counter.value = 0;
};
</script>

<template>
  <UCard class="w-1/4">
    <template #header>
      <p>CounterApp</p>
    </template>
    <div class="text-center text-4xl mb-4">{{ counter }}</div>
    <div class="flex gap-x-3 justify-between">
      <UButton @click="inclease">inclease</UButton>
      <UButton @click="declease">declease</UButton>
      <UButton @click="reset">Reset</UButton>
    </div>
  </UCard>
</template>
