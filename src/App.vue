<template>
  <div class="app">
    <p>{{jobs[0].title}}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent,  ref } from 'vue';
import Job from './models/job';

export default defineComponent({
  name: 'App',
  components: {
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
          id: '1'
        },  
        {
          title: "VueJs Developer",
          location: "Long Island",
          salary: 50000,
          id: '1'
        },  
        {
          title: "NodeJs Developer",
          location: "Remote",
          salary: 50000,
          id: '1'
        },  
      ])

      return {jobs}
    },
  
});
</script>

<style>

</style>
