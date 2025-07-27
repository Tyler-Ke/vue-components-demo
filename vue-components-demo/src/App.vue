<template>
   <div>{{ message }}</div>
   <contact-us></contact-us>
   <ButtonCounter></ButtonCounter>
   <ButtonCounter></ButtonCounter>
</template>

<script setup>
   import ButtonCounter from "./components/ButtonCounter.vue"
   const message = "Hello Vue";
</script>

<style>

</style>