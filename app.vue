<script setup lang="ts">
const value = ref('')
const columns = [{
  key: 'id',
  label: 'ID'
}, {
  key: 'task',
  label: 'Task'
}, {
  key: 'status',
  label: 'Status'
}, {
  key: 'manage',
  label: 'Manage'
}]

const people = [{
  id: 1,
  task: 'Study Nuxt 3',
  status: 'Not Finished',
  manage: 'Member'
}, {
  id: 2,
  task: 'Buy some snacks',
  status: 'Finished',
  manage: 'Admin'
}, {
  id: 3,
  task: 'Cook dinner',
  status: 'Not Finished',
  manage: 'Member'
},]
</script>


<template>
  <UContainer>
    <UCard class="mt-10">
      <template #header>
        <div class="flex justify-between">
          <h1>Welcome to Nuxt Todo App</h1>
        </div>
      </template>
      <div class="flex justify-between pb-8 gap-2">
        <div class="w-full">
          <UInput v-model="value" placeholder="Write your status" size="lg" />
        </div>
        <UButton>Submit</UButton>
      </div>
      <div class="pb-8">
        Todo Lists
        <UTable :columns="columns" :rows="people" />
      </div>
      <UButton icon="i-heroicons-book-open" to="https://ui.nuxt.com" target="_blank">Open Creator's GitHub</UButton>
    </UCard>
  </UContainer>
</template>
