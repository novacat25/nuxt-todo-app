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

<script setup lang="ts">
defineProps(["mission"])
const columns = [{
    key: 'id',
    label: 'ID',
    class: 'w-2'
}, {
    key: 'task',
    label: 'Task',
    class: 'w-1/2'
}, {
    key: 'created_at',
    label: 'Registered Date',
    class: 'w-1/6'
}, {
    key: 'updated_at',
    label: 'Modified Date',
    class: 'w-1/6'
}, {
    key: 'status',
    label: 'Status',
    class: 'w-1/6'
}, {
    key: 'actions'
}]

const tasks = [{
    id: 1,
    task: 'Study Nuxt 3',
    created_at: '2024-05-03 09:30:00',
    updated_at: '2024-09-17 00:00:00',
    status: 'Not Finished'
}, {
    id: 2,
    task: 'Buy some snacks',
    created_at: '2024-05-03 09:30:00',
    updated_at: '2024-09-17 00:00:00',
    status: 'Finished'
}, {
    id: 3,
    task: 'Cook dinner',
    created_at: '2024-05-09 00:00:00',
    updated_at: '2024-09-17 00:00:00',
    status: 'Not Finished'
},]

const handleDoneClick = (value?: Object) => {
    console.log("DONE", value)
}
const handleDeleteClick = (value?: Object) => {
    console.log("DELETE", value)
}
</script>
