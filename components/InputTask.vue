<script setup lang="ts">
    const value = ref('')
</script>

<template>
    <div class="flex justify-between pb-8 gap-2">
        <div class="w-full">
          <UInput v-model="value" placeholder="Write your status" size="lg" />
        </div>
        <UButton>Submit</UButton>
      </div>
</template>

