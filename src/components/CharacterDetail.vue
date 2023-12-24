<script setup lang="ts">

// import { ref, onMounted } from 'vue';
import "./../assets/characters.css"
import { useRouter } from 'vue-router';

import { defineProps } from 'vue';

const props = defineProps(['item']);

const router = useRouter();

const changeRoute = (item:any) => {

    const details = {name: props.item.name, image: props.item.image}
    router.push({ name: 'about', state: { details } });
}


</script>



<template>
    <!-- <v-card class="mx-auto" max-width="200" height="200" title="Card title" theme="dark"> -->
        <img :src="props.item.image" />
        <button @click="changeRoute">  click </button>
        <!-- <router-link :to="{ name: 'about',  params: { character: props.item}  }">
            hi
            </router-link> -->
    <!-- </v-card> -->
  
</template>


