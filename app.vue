<script setup lang="ts">
import type { Task } from './types/task'

useHead({
  title: 'NovaCat\'s Todo App',
  meta: [
    { name: 'description', content: 'To write, and manage tasks. This app is built by Nuxt 3 and Vue.js.' }
  ]
})

const mission = ref('')

const todos = ref<Task[]>([{
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

//read at first, don't update dynamically
let NEW_ID_NUM = todos.value.length

const handleInputTask = (value: string) => {
  NEW_ID_NUM += 1
  const currentDate = new Date().toISOString().split('T')[0]
  const newItem =
  {
    id: NEW_ID_NUM,
    task: value,
    date: currentDate,
    status: 'Not Finished'
  }

  todos.value.push(newItem)
}

const handleDeleteTask = (task: Task) => {
  const deletedResult = todos.value.filter((todo) => todo.id != task.id)
  todos.value = deletedResult
}
</script>

<template>
  <UContainer>
    <UCard class="mt-10">
      <template #header>
        <Header />
      </template>
      <input-task @add="handleInputTask" />
      <todo-list @delete="handleDeleteTask" :todos :mission />
      <Footer />
    </UCard>
  </UContainer>
</template>