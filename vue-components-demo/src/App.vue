<template>
   <div class="container">
      <div>{{ message }}</div>
      <Contact name="Tyler" :phone="1231231234" :ownername="contactsOwner"></Contact>
      <Contact name="Vincent" :phone="1231231235" :ownername="contactsOwner" email="vincentsemail@gmail.com"></Contact>
   </div>
</template>

<script setup>
import Contact from "./components/Contact.vue";
const message = "Hello Vue";
const contactsOwner = "gooogle";
</script>

<style></style>
