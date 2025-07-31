<template>
   <div class="bg-black text pt-3" :style="{ height: '100vh' }">
      <h1 class="text-center text-success">Contact Page</h1>
      <div class="container">
         <div class="row text-white p-2 mb-2">
            <div class="col-6">
               Owner Name: <input v-model="ownerName" />
            </div>
            <div class="col-6 text-end">
               Max Lucky Number: <input v-model="maxNumber"></input>
            </div>
         </div>
         <br /><br />
         <AddContact @add-contact="onAddContact($event)"></AddContact>
         <div class="row">
            <div class="col-12" v-for="contact in contacts" :key="contact.name">
               <Contact
                  :name="contact.name"
                  :phone="contact.phone"
                  :ownername="contact.ownerName"
                  :email="contact.email"
                  :isFavorite="contact.isFavorite"
                  @update-favorite="
                     contact.isFavorite = onUpdateFavorite(
                        $event,
                        contact.phone
                     )
                  "
               ></Contact>
            </div>
         </div>
      </div>
   </div>
</template>

<script setup>
import { reactive, ref, provide } from "vue";
import Contact from "./components/Contact.vue";
import AddContact from "./components/AddContact.vue";
const ownerName = ref("Alphabet Inc");
const maxNumber = ref(100);
provide("maxLuckyNumber", maxNumber);
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
]);

function onAddContact(contact) {
   contact.ownerName = ownerName.value;
   contact.isFavorite = false;
   contacts.push(contact);
}

function onUpdateFavorite(oldValueFromChildComponent, phoneNumberFromParent) {
   console.log(oldValueFromChildComponent);
   return !oldValueFromChildComponent.isFavorite;
}
</script>

<style></style>
