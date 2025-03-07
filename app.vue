<script setup lang="ts">
import type { Task } from './types/task'

useHead({
  title: 'NovaCat\'s Todo App',
  meta: [
    { name: 'description', content: 'To write, and manage tasks. This app is built by Nuxt 3 and Vue.js.' }
  ]
})

const mission = ref('')

const todos = ref<Task[]>([])

const initialDataFetch = () => {

  const fetchFromLocalStorage = localStorage.getItem("todo")

  if (fetchFromLocalStorage) {
    const fetchedToDo: Task[] = JSON.parse(fetchFromLocalStorage)
    todos.value = fetchedToDo
  } else {
    todos.value = []
  }

}

initialDataFetch()

const generateTaskID = (): number => {
  let TEMP_TASK_ID = 0
  todos.value.forEach((todo) => {
    TEMP_TASK_ID = Math.max(TEMP_TASK_ID, todo.id)
  })
  return TEMP_TASK_ID
}


//read at first, don't update dynamically
let NEW_TASK_ID = generateTaskID()

const handleInputTask = (value: string) => {
  NEW_TASK_ID += 1
  const currentDate = new Date().toISOString().split('T')[0]

  const newItem =
  {
    id: NEW_TASK_ID,
    task: value,
    date: currentDate,
    status: 'Not Finished'
  }

  todos.value.push(newItem)

  refreshTaskStatus()
}

const refreshTaskStatus = () => {
  const serialisedArray = JSON.stringify(todos.value)
  localStorage.setItem("todo", serialisedArray)
}

const handleDeleteTask = (task: Task) => {
  const deletedResult = todos.value.filter((todo) => todo.id != task.id)
  todos.value = deletedResult

  refreshTaskStatus()
}
</script>

<template>
  <UContainer>
    <UCard class="mt-10">
      <template #header>
        <Header />
      </template>
      <input-task @add="handleInputTask" />
      <todo-list @update="refreshTaskStatus" @delete="handleDeleteTask" :todos :mission />
      <Footer />
    </UCard>
  </UContainer>
</template>