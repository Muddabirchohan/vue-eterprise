<script setup lang="ts">


import { ref, onMounted  } from 'vue';

interface ListItem {
  userId: number;
  id: number;
  title: string;
  body: string;
}

const listItems = ref<ListItem[]>([]);
const isLoading = ref<boolean>(true)

async function getData() {
    try{
    const res = await fetch("https://jsonplaceholder.typicode.com/posts");
    const finalRes = await res.json();
    listItems.value = finalRes;
    }finally{
        isLoading.value = false;
    }

}

getData()

onMounted(getData);


</script>

<template>
      <div v-if="isLoading">Loading...</div>
    <div v-for="item in listItems">
     {{item.title}}
   </div>
</template>

