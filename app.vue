<script setup lang="ts">
const value = ref('')
const columns = [{
  key: 'id',
  label: 'ID'
}, {
  key: 'name',
  label: 'Task'
}, {
  key: 'title',
  label: 'Status'
}, {
  key: 'role',
  label: 'Control'
}]

const people = [{
  id: 1,
  name: 'Lindsay Walton',
  title: 'Front-end Developer',
  role: 'Member'
}, {
  id: 2,
  name: 'Courtney Henry',
  title: 'Designer',
  role: 'Admin'
}, {
  id: 3,
  name: 'Tom Cook',
  title: 'Director of Product',
  role: 'Member'
}, {
  id: 4,
  name: 'Whitney Francis',
  title: 'Copywriter',
  role: 'Admin'
}, {
  id: 5,
  name: 'Leonard Krasner',
  title: 'Senior Designer',
  role: 'Owner'
}, {
  id: 6,
  name: 'Floyd Miles',
  title: 'Principal Designer',
  role: 'Member'
}]
</script>


<template>
  <UContainer>
    <UCard class="mt-10">
      <template #header>
        <div class="flex justify-between">
          <h1>Welcome to Nuxt Todo App</h1>
        </div>
      </template>
      <div class="flex justify-between pb-8">
        <div class="w-9/12">
          <UInput v-model="value" placeholder="Write your tasks" />
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
