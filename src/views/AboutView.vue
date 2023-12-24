<script setup lang="ts">

// import { ref, onMounted } from 'vue';
import "./../assets/characters.css"

import { useRouter } from "vue-router";


const router = useRouter();

console.log("router details",router.options.history.state)


const user:any = router.options.history.state.details;

</script>


<template>
  <div class="about">
    <h1>about page fixes </h1>
    <p> {{user?.name}} </p>
    <img :src="user.image"/>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
