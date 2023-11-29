<script setup>
import { ref } from 'vue';
import TaskComponent from '@/components/TaskComponent.vue';

const task= ref(['Estudiar','sacar 5','decansar'])

function deleteTask(index){
  // console.log('Borrar hijo',index)
  task.value.splice(index,1)
}

</script>

<template>
  <div class="gb-gray-50 w-96 shadow-md rounded mt-12 mx-auto py-4 px-3">
    <h1 class=" text-2xl font-semibold mx-auto ">Tareas</h1>

    <div class="flex mt-2">
      <input class="w-4/5 h-8 px-2 border rounded rounded-r-none border-green-500" type="text">
      <span class="w-1/5 bg-green-500 text-center  rounded-l-none text-xl rounded-3xl  hover:bg-green-600 hover:cursor-pointer"
      >+</span>
    </div>
    <TaskComponent v-for="(obj,index) in task" :key="index" :tarea="obj" :index="index" @borrarTarea="deleteTask"></TaskComponent>

    
  </div>

</template>

<style scoped>

</style>
