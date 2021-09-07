<template>
  <div class="app">
  <header>
    <div class="order">
      <button @click="handleClick('title')">Order by Title</button>
      <button @click="handleClick('salary')">Order by Salary</button>
      <button @click="handleClick('location')">Order by Location</button>
    </div>
  </header>
  
    <JobsList :jobs="jobs" :order="order"/>
  </div>
</template>

<script lang="ts">
import { defineComponent,  ref } from 'vue';
import Job from './models/job';
import OrderTerm from './models/OrderTerm';
import JobsList from '@/components/JobsList.vue';

export default defineComponent({
  name: 'App',
  components: {
    JobsList,
  },
  setup() {
     

      const jobs  = ref<Job[]>([
        {
          title: "Flutter Developer",
          location: "Remote",
          salary: 50000,
          id: '1'
        },  
        {
          title: "React Developer",
          location: "Onsite",
          salary: 30000,
          id: '2'
        },  
        {
          title: "VueJs Developer",
          location: "Long Island",
          salary: 50000,
          id: '3'
        },  
        {
          title: "NodeJs Developer",
          location: "Remote",
          salary: 50000,
          id: '4'
        },  
      ])


      //local state to store the chosen order term
      //set it initially to title
      const order = ref<OrderTerm>('title')

      const handleClick=(term: OrderTerm)=> {
        order.value = term;
      }

      return {jobs, handleClick, order}
    },
  
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
</style>
