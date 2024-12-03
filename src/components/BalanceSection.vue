<template>
  <div class="balance">
    <h2>your balance</h2>
    <p>${{ totalIncome + totalExpenses }}</p>
  </div>
  <div class="card">
    <div class="card-child">
      <h3>income</h3>
      <p>${{ totalIncome }}</p>
    </div>
    <div class="border"></div>
    <div class="card-child">
      <h3>Expense</h3>
      <p>${{ totalExpenses }}</p>
    </div>
  </div>
</template>

<script setup>
import { computed, inject, ref,watch } from 'vue';
const expenses = ref([]);
const incomes = ref([]);
const receveidData = inject('tData');

incomes.value = receveidData.value.filter((item) => item.amount > 0);
expenses.value = receveidData.value.filter((item) => item.amount < 0);

watch(
  () => receveidData.value,
  (newData) => {
    incomes.value = newData.filter((item) => item.amount > 0);
    expenses.value = newData.filter((item) => item.amount < 0);
  },
  { immediate: true } // Run the watcher immediately
);

const totalIncome = computed(() => {
 return  incomes.value.reduce((sum, acc) => sum + acc.amount, 0);
});

const totalExpenses = computed(() => {
 return  expenses.value.reduce((sum, acc) => sum + acc.amount, 0);
});
</script>

<style scoped>
.balance {
  width: 400px;
}
h2,
p {
  font-size: 4rem;
  font-weight: 400;
  text-transform: uppercase;
}
P {
  font-weight: 500;
  font-size: 4rem;
}
.card {
  margin-block: 2rem;
  box-shadow: 0 5px 10px rgb(44, 13, 10);
  display: flex;
  padding: 2rem;
  justify-content: space-around;
  .card-child {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 1rem;
  }
}
.border {
  border-right: 1px solid rgb(174, 170, 170);
}
h3 {
  font-size: 3rem;
  text-transform: uppercase;
  text-align: center;
}
</style>
