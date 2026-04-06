<template>
  <div class="app">
    <h1>가계부</h1>
    <ExpenseForm @add-expense="addExpense"/>
  </div>
</template>

<script setup>
import ExpenseForm from './components/ExpenseForm.vue';
import { ref } from 'vue';

const expenses = ref([]) // 빈 배열로 시작

const addExpense = (expense) => {
  // expense 배열에 추가하려면?
  expenses.value.push(expense)
}

</script>