<script setup lang="ts">
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

const tasks = [{
    id: 1,
    task: 'Study Nuxt 3',
    date: '2024-05-03',
    status: 'Not Finished'
}, {
    id: 2,
    task: 'Buy some snacks',
    date: '2024-05-03',
    status: 'Finished'
}, {
    id: 3,
    task: 'Cook dinner',
    date: '2024-05-09',
    status: 'Not Finished'
},]
</script>

<template>
    <UTable :columns="columns" :rows="tasks" class="px-4">
        <template #actions-data="">
            <div class="flex gap-2 justify-end">
                <UButton color="blue">DONE</UButton>
                <UButton color="red">DELETE</UButton>
            </div>
        </template>
    </UTable>
</template>