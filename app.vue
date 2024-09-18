<template>
  <UContainer>
    <UCard class="mt-10">
        <template #header>
          <Header />
        </template>
        <InputTask @add="handleClick" />
        <TodoList :mission />
        <Footer />
    </UCard>
  </UContainer>
</template>

<script setup lang="ts">
useHead({
  title: 'NovaCat\'s Todo App',
  meta: [
    { name: 'description', content: 'To write, and manage tasks. This app is built by Nuxt 3 and Vue.js.' }
  ]
})

  const mission = ref('')

  const handleClick = (value?: string) => {
    mission.value = value ?? ''
  }
</script>