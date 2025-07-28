<template>
   <div class="container">
      <div>{{ message }}</div>
      Contact Owner Name: <input v-model="ownerName" />
      <div class="row">
         <div class="col-12" v-for="contact in contacts" :key="contact.name">
            <Contact
               :name="contact.name"
               :phone="contact.phone"
               :ownername="contact.ownerName"
               :email="contact.email"
               :isFavorite="contact.isFavorite"
            ></Contact>
         </div>
      </div>
   </div>
</template>

<script setup>
import {reactive, ref} from "vue";
import Contact from "./components/Contact.vue";
const message = "Hello Vue";
const ownerName = ref("Alphabet Inc");
const contacts = reactive([
   {
      name: "Tyler",
      phone: 1231231234,
      ownerName: ownerName,
      isFavorite: false,
   },
   {
      name: "Vincent",
      phone: 5554448888,
      ownerName: ownerName,
      isFavorite: true,
   },
   {
      name: "Aaron",
      phone: 9912345671,
      ownerName: "",
      email: "blackie1234@gmail.com",
      isFavorite: false,
   },
])
</script>

<style></style>
