<script setup lang="ts">
const columns = [{
    key: 'id',
    label: 'ID'
}, {
    key: 'task',
    label: 'Task'
}, {
    key: 'date',
    label: 'Register Date'
}, {
    key: 'status',
    label: 'Status'
}]

const people = [{
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
    <div class="pb-8">
        Todo Lists
        <UTable :columns="columns" :rows="people" />
    </div>
</template>