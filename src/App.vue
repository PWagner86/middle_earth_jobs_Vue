<template>
  <header>
    <div class="title">
      <img src="./assets/one_ring.png" alt="the one ring">
      <h1>Middle-earth Jobs</h1>
    </div>
    <div class="order">
      <button @click="handleClick('title')">order by title</button>
      <button @click="handleClick('salary')">order by salary</button>
      <button @click="handleClick('location')">order by location</button>
    </div>
  </header>
  <JobList :jobs="jobs" :order="order" />
</template>

<script lang="ts">
import {defineComponent, ref} from 'vue';
import Job from "@/types/Job";
import JobList from '@/components/JobList.vue';
import OrderTerm from '@/types/OrderTerm';

export default defineComponent({
  name: 'App',
  components: {JobList},
  setup: function () {
    const order = ref<OrderTerm>('title')

    const jobs = ref<Job[]>([
      {title: 'slave-driver', location: 'dol guldur', salary: 5000, id: 1},
      {title: 'gardener', location: 'fangorn', salary: 4000, id: 2},
      {title: 'blacksmith', location: 'erebor', salary: 3500, id: 3},
      {title: 'solider', location: 'minas tirith', salary: 3600, id: 4},
      {title: 'bartender', location: 'prancing pony', salary: 2000, id: 5},
    ])

    const handleClick = (sortTerm: OrderTerm) => {
      order.value = sortTerm;
    }

    return {jobs, order, handleClick}
  }
});
</script>

<style>
header {
  text-align: center;
}

header .order {
  margin-top: 20px;
}

button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}

header .title {
  display: flex;
  justify-content: center;
}

header img {
  height: 100px;
  margin-right: 20px;
}

header h1 {
  font-size: 3em;
}
</style>