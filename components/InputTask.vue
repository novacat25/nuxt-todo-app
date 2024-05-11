<script setup lang="ts">
    const value = ref('')
    const handleClick = ( value: String ): void => {
      console.log("the inputed value is", value)
    }
</script>

<template>
    <div class="flex justify-between pb-8 gap-2 px-5">
        <div class="w-full">
          <UInput v-model="value" placeholder="Write your tasks" size="lg" />
        </div>
        <UButton @click="handleClick(value)">Submit</UButton>
      </div>
</template>

