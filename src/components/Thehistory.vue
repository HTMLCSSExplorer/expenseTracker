<template>
  <div class="history">
    <h2>history</h2>
    <ul class="list" v-for="data in receivedData" :key="data.id">
      <li>
        <span class="fas fa-x btn-x" @click="removeItem(data.id)"></span>
        {{ data.transactionname }}
        <span class="price"> $ {{ data.amount }}</span>
        <span
          class="led"
          :class="data.amount > 0 ? 'led-green' : 'led-red'"
        ></span>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { inject } from 'vue';
const emit = defineEmits(['removeList']);
const receivedData = inject('tData');
const removeItem = (id) => {
  emit('removeList', id);
};
</script>

<style scoped>
.history {
  margin-top: 5rem;
}
h2 {
  font-size: 4rem;
  text-transform: capitalize;
  border-bottom: 1px solid rgb(97, 96, 96);
  padding-block: 2rem;
}
.list {
  list-style: none;
  li {
    font-size: 2rem;
    display: block;
    box-shadow: 0 0 5px black;
    margin-block: 2rem;
    border-radius: 5px;
    text-transform: capitalize;
    display: flex;
    justify-content: space-between;
    padding-left: 0.5rem;
    align-items: center;
    position: relative;
    flex-grow: 1;
    .price {
      margin-left: auto;
    }
    .led {
      width: 10px;
      margin: 0;
      height: 50px;
      margin-left: 10px;
    }
    .led-red {
      background: red;
    }
    .led-green {
      background: rgb(39, 199, 15);
    }
    .btn-x {
      position: absolute;
      right: calc(100% + 15px);
      color: red;
      opacity: 0;
      transition: all 0.3s;
      cursor: pointer;
    }
    &:hover .btn-x {
      opacity: 1;
    }
  }
}
</style>
