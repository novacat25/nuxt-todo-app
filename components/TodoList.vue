<script setup lang="ts">
import type { Task } from '~/types/task'
const emits = defineEmits<{ (e: 'delete', task: Task): void }>()
defineProps(["mission", "todos"])

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
    emits('delete',task)
}

</script>

<template>
    {{ mission }}
    <UTable :columns="columns" :rows="todos" class="px-4">
        <template #actions-data="{ row }">
            <div class="flex gap-2 justify-end">
                <!-- TODO: change 'Not Finished' to 'false' -->
                <UButton v-if="row.status === 'Not Finished'" color="blue" @click="handleDoneClick(row)">DONE</UButton>
                <UButton color="red" @click="handleDeleteClick(row)">DELETE</UButton>
            </div>
        </template>
    </UTable>
</template>
