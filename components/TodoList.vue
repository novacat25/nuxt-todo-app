<script setup lang="ts">
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

const handleDoneClick = (value?: Object) => {
    console.log("DONE", value)
}
const handleDeleteClick = (value?: Object) => {
    console.log("DELETE", value)
}
</script>

<template>
    {{ mission }}
    <UTable :columns="columns" :rows="tasks" class="px-4">
        <template #actions-data="{ row }">
            <div class="flex gap-2 justify-end">
                <UButton v-if="row.status === 'Not Finished'" color="blue" @click="handleDoneClick(row)">DONE</UButton>
                <UButton color="red" @click="handleDeleteClick(row)">DELETE</UButton>
            </div>
        </template>
    </UTable>
</template>