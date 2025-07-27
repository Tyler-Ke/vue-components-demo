<template>
   <div class="container">
      <div>{{ message }}</div>
      <Contact name="Tyler" phone="123-123-1234"></Contact>
   </div>
</template>

<script setup>
   import ButtonCounter from "./components/ButtonCounter.vue"
   import Contact from "./components/Contact.vue"
   const message = "Hello Vue";
</script>

<style>

</style>