<script setup lang="ts">
  const mission = ref('')

  const handleClick = (value?: string) => {
    mission.value = value ?? ''
    console.log("mission", mission.value)
  }
</script>

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
