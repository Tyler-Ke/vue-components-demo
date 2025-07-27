<template>
   <div class="bg-info rounded p-4 m-2">
      <h3>Name: {{ name }}</h3>
      <p>Email: {{ email }}</p>
      <p>Phone: {{ phone }}</p>
      <p class="float-end small" v-if="ownername !== ''">This contact belongs to: {{ ownername }}</p>
   </div>
</template>

<script setup>
   import {ref, defineProps} from "vue";
   const email = ref("fakeemail2@gmail.com");
   const props = defineProps(["name", "phone", "ownername"]);
</script>