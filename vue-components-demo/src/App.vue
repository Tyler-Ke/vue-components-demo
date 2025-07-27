<template>
   <div>{{ message }}</div>
   <ContactUs></ContactUs>
   <ButtonCounter></ButtonCounter>
   <ButtonCounter></ButtonCounter>
</template>

<script setup>
   import ButtonCounter from "./components/ButtonCounter.vue"
   import ContactUs from "./components/ContactUs.vue"
   const message = "Hello Vue";
</script>

<style>

</style>