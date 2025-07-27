<template>
   <div class="container">
      <div>{{ message }}</div>
      <Contact
         name="Tyler"
         :phone="123-123-1234"
         :ownername="contactsOwner"
      ></Contact>
   </div>
</template>

<script setup>
import Contact from "./components/Contact.vue";
const message = "Hello Vue";
const contactsOwner = "gooogle";
</script>

<style></style>
