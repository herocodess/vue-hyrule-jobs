<template>
  <div class="app">
    <JobsList :jobs="jobs"/>
  </div>
</template>

<script lang="ts">
import { defineComponent,  ref } from 'vue';
import Job from './models/job';
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

      return {jobs}
    },
  
});
</script>

<style>

</style>
