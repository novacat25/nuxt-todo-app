<script setup lang="ts">
import type { Task } from '~/types/task'

defineProps(["mission", "tasks"])

const columns = [{
    key: 'id',
    label: 'ID',
    class: 'w-2'
}, {
    key: 'task',
    label: 'Task',
    class: 'w-1/2'
}, {
    key: 'date',
    label: 'Register Date'
}, {
    key: 'status',
    label: 'Status'
}, {
    key: 'actions'
}]

const handleDoneClick = (task: Task) => {
   task.status = "Finished"
}
const handleDeleteClick = (task: Task) => {
    console.log("DELETE", task)
}
</script>

<template>
    {{ mission }}
    <UTable :columns="columns" :rows="tasks" class="px-4">
        <template #actions-data="{ row }">
            <div class="flex gap-2 justify-end">
                <!-- TODO: change 'Not Finished' to 'false' -->
                <UButton v-if="row.status === 'Not Finished'" color="blue" @click="handleDoneClick(row)">DONE</UButton>
                <UButton color="red" @click="handleDeleteClick(row)">DELETE</UButton>
            </div>
        </template>
    </UTable>
</template>