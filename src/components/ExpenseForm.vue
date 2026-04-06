<template>
    <div class="form">
        <input v-model="description" type="text" placeholder="내용을 입력하세요."> &nbsp;
        <input v-model="amount" type="number" placeholder="금액을 입력하세요."> &nbsp;
        <select v-model="type">
            <option value="income">수입</option>
            <option value="expense">지출</option>
        </select>
        <button @click="handleSubmit()">추가</button>
    </div>
</template>

<script setup>
import { ref } from 'vue';

const description = ref('');
const amount = ref(0);
const type = ref('expense');

const emit = defineEmits(['add-expense'])

const handleSubmit = () => {
    emit('add-expense', {
        description : description.value,
        amount : amount.value,
        type : type.value
    })

    // 초기화
    description.value = ''
    amount.value = 0
    type.value = 'expense'
}

</script>