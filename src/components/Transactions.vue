<template>
  <div class="transaction">
    <h2>Add new transaction</h2>
    <form action="">
      <div class="form-control">
        <label for="">Text</label>
        <input type="text" placeholder="enter text" />
      </div>
      <div class="form-control">
        <label for="">Amount (negative - expense, positive - income)</label>
        <input type="number" placeholder="enter amount" />
      </div>
      <button>add transaction</button>
    </form>
  </div>
</template>

<script setup></script>

<style scoped>
.transaction {
  margin-top: 5rem;
}
h2 {
  font-size: 3rem;
  border-bottom: 1px solid black;
}
.form-control {
  padding: 1rem 2rem;
  display: flex;
  flex-direction: column;
  margin-block: 3rem;
  label {
    font-size: 3rem;
  }
  input {
    border: 0;
    box-shadow: 0 0 5px rgb(143, 143, 143);
    padding: 1rem 2rem;
    font-size: 3rem;
    margin-top: 1rem;
    text-transform: capitalize;
    outline: 0;
  }
  ::placeholder {
    font-size: 3rem;
    text-transform: capitalize;
  }
}
button {
  width: 100%;
  border: 0;
  background: #9c88ff;
  color: white;
  padding: 2rem 4rem;
  text-transform: capitalize;
  font-size: 2rem;
  cursor: pointer;
  transition: all 0.1s;
  &:hover {
    scale: 1.02;
  }
}
</style>
