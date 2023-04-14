<template>
  <div class="app">
    <button @click="handleclick('title')">order by title</button>
    <button @click="handleclick('location')">order by location</button>
    <button @click="handleclick('salary')">order by salary</button>

    <JobList :jobs="jobs" :order="order"></JobList>
    <!-- <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('swarup')">change the name</button>
    <button @click="changeage('30')">change the age</button> -->
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import JobList from './components/JobList.vue'
import Job from './types/Job'
import OrderTerm from './types/OrderTerm'




export default defineComponent({
  name: 'App',
  components: {
  JobList
  },
  // data(){
  //   return {
  //     name :"Suyog",
  //     age:35 as number | string,
  //   }
  // },
  // methods:{
  //   changeName(name:string){
  //     this.name = name;
  //   },
  //   changeage(age:number | string){
  //     this.age = age;
  //   }
    
  // }
  setup() {
    
    const jobs =ref<Job[]>([{
      title: "Software Engineer",
      location:"Euprope",
      salary: 100000,
      id: '1',
     },
     {
      title: "Blockchain Engineer",
      location:"Euprope",
      salary: 120000,
      id: '2',
     },{
      title: "Software Design Engineer",
      location:"USA",
      salary: 30000,
      id: '3',
     },{
      title: "Software Artiect",
      location:"Japan",
      salary: 90000,
      id: '4',
     },
     {
      title: "Full stack",
      location:"Abu dhabi",
      salary: 1000000,
      id: '5',
     }]);
     const order=ref<OrderTerm>("title")
     const handleclick=(term:OrderTerm) => {
      order.value=term
     }
     return {
       jobs,handleclick,order
     }
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
