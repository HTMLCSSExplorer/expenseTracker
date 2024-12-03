<template>
  <main class="container">
    <TheHeader></TheHeader>
    <BalanceSection></BalanceSection>
    <Thehistory @removeList="removeList"></Thehistory>
    <Transactions
      @submitTransactionData="getTransactionData"
      @clearAll="clearAll"
    ></Transactions>
  </main>
</template>

<script setup>
import BalanceSection from './components/BalanceSection.vue';
import TheHeader from './components/TheHeader.vue';
import Thehistory from './components/Thehistory.vue';
import Transactions from './components/Transactions.vue';
import { provide, ref } from 'vue';

const transactions = ref([]);
const dataFromStorage = () => {
  const data = JSON.parse(localStorage.getItem('tData'));
  if (data !== null) {
    transactions.value = data;
  }
};

const removeList = (id) => {
  const dataFromStorage = JSON.parse(localStorage.getItem('tData'));
  const newData = dataFromStorage.filter((item) => item.id !== id);
  console.log(newData);
  transactions.value = newData;
  localStorage.setItem('tData', JSON.stringify(newData));
};
dataFromStorage();
const getTransactionData = (amount, name) => {
  const newTransactopn = {
    id: Math.random().toString(32).slice(2),
    amount: amount,
    transactionname: name,
  };

  updateLocalStorage(newTransactopn);
};

const updateLocalStorage = (newTransactopn) => {
  const dataFromStorage = JSON.parse(localStorage.getItem('tData')) || [];
  const updatedData = [...dataFromStorage, newTransactopn];
  localStorage.setItem('tData', JSON.stringify(updatedData));
  transactions.value = updatedData;
};

provide('tData', transactions);
const clearAll = () => {
  localStorage.clear();
  transactions.value = [];
};
// localStorage.clear();
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
html {
  font-size: 62.5%;
}
body {
  font-family: 'Roboto', 'sans-serif';
}
.container {
  max-width: 700px;
  margin: auto;
}
</style>
