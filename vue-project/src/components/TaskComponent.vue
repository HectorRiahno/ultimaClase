<script setup>
const props =defineProps({
    tarea:{
        type:String,
        default:'tarea indefinida'
    },
    index:{
        type:Number
    }
})
const emit= defineEmits(['borrartarea'])

function borrarTarea(index){
//   console.log('borrar tarea',index)
  emit('borrarTarea',index)
}
</script>
<template>
<div class=" flex justify-between mt-3 bg-gray-200 rounded px-4 py-1 ">
        {{ props.tarea }}
      <span class="px-2 bg-red-500 text-center text-lg rounded  hover:bg-red-600 hover:cursor-pointer" @click="borrarTarea(props.index)">X</span>
    </div>
</template>