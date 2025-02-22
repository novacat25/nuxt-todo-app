<script setup lang="ts">
import type { Task } from './types/task'

  useHead({
    title: 'NovaCat\'s Todo App',
    meta: [
      { name: 'description', content: 'To write, and manage tasks. This app is built by Nuxt 3 and Vue.js.' }
    ]
  })

  const mission = ref('')

  const tasks = ref<Task[]>([{
    id: 1,
    task: 'Study Nuxt 3',
    date: '2024-05-03',
    status: 'Not Finished'
}, {
    id: 2,
    task: 'Buy some snacks',
    date: '2024-05-03',
    status: 'Finished'
}, {
    id: 3,
    task: 'Cook dinner',
    date: '2024-05-09',
    status: 'Not Finished'
},])

  const handleInputTask = (value: string) => {
    const NEW_ID_NUM = tasks.value.length
    const newItem = 
    {
      id: NEW_ID_NUM + 1,
      task: value,
      date: '2025-02-22',
      status: 'Not Finished'
    }

    tasks.value.push(newItem)
  }
</script>

<template>
  <UContainer>
    <UCard class="mt-10">
        <template #header>
          <Header />
        </template>
        <InputTask @add="handleInputTask" />
        <TodoList :tasks :mission />
        <Footer />
    </UCard>
  </UContainer>
</template>