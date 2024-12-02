<template>
  <div class="balance">
    <h2>your balance</h2>
    <p>$240</p>
  </div>
  <div class="card">
    <div class="card-child">
      <h3>income</h3>
      <p>$0.00</p>
    </div>
    <div class="border"></div>
    <div class="card-child">
      <h3>Expense</h3>
      <p>$0.00</p>
    </div>
  </div>
</template>

<script setup></script>

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
