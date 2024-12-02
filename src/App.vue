<template>
  <main class="container">
    <TheHeader></TheHeader>
    <BalanceSection></BalanceSection>
    <Thehistory></Thehistory>
    <Transactions></Transactions>
  </main>
</template>

<script setup>
import BalanceSection from './components/BalanceSection.vue';
import TheHeader from './components/TheHeader.vue';
import Thehistory from './components/Thehistory.vue';
import Transactions from './components/Transactions.vue';
</script>

<style>
@import url(https://fonts.googleapis.com/css?family=Roboto:100,100italic,300,300italic,regular,italic,500,500italic,700,700italic,900,900italic);
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
