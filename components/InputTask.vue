<script setup lang="ts">
    const inputValue = ref<string>('')
    const emits = defineEmits<{(e: 'add',task?: string): void}>()
    const handleClick = ( value?: string ): void => {
      emits('add',value)
    }
</script>

<template>
    <div class="flex justify-between pb-8 gap-2 px-5">
        <div class="w-full">
          <UInput v-model="inputValue" placeholder="Write your tasks" size="lg" />
        </div>
        <UButton @click="handleClick(inputValue)">Submit</UButton>
      </div>
</template>

