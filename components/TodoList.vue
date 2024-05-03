<script setup lang="ts">
const columns = [{
    key: 'id',
    label: 'ID'
}, {
    key: 'task',
    label: 'Task'
}, {
    key: 'status',
    label: 'Status'
}, {
    key: 'manage',
    label: 'Manage'
}]

const people = [{
    id: 1,
    task: 'Study Nuxt 3',
    status: 'Not Finished',
    manage: 'Member'
}, {
    id: 2,
    task: 'Buy some snacks',
    status: 'Finished',
    manage: 'Admin'
}, {
    id: 3,
    task: 'Cook dinner',
    status: 'Not Finished',
    manage: 'Member'
},]
</script>

<template>
    <div class="pb-8">
        Todo Lists
        <UTable :columns="columns" :rows="people" />
    </div>
</template>