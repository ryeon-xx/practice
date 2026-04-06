<template>
    <ul>
        <li v-for="expense in expenses" :key="expense.id">
            {{ expense.description }}
            {{ expense.amount }}
            {{ expense.type === 'expense' ? '지출' : '수입' }}
        </li>
    </ul>
</template>

<script setup>
const props = defineProps(['expenses'])
</script>