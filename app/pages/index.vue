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
  <UHeader />
  <UContainer class="py-12">
    <h2>{{ counter }}</h2>
    <div class="flex gap-x-3">
      <UButton @click="inclease">inclease</UButton>
      <UButton @click="declease">declease</UButton>
      <UButton @click="reset">Reset</UButton>
    </div>
  </UContainer>
</template>
