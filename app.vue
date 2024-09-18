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
  const mission = ref('')

  const handleClick = (value?: string) => {
    mission.value = value ?? ''
  }
</script>