<template>
   <div class="bg-info rounded p-2 m-2">
      <h1>Contact Us</h1>
      <p>Please send us an email at {{ email }}</p>
   </div>
</template>

<script setup>
   import {ref} from "vue";
   const email = ref("fakeemail2@gmail.com")
</script>