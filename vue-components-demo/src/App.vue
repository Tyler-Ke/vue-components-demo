<template>
   <div class="bg-black text pt-3">
      <div class="container">
         <div class="text-white float-end">
            Contact Owner Name: <input v-model="ownerName" />
         </div>
         <br /><br />
         <AddContact></AddContact>
         <div class="row">
            <div class="col-12" v-for="contact in contacts" :key="contact.name">
               <Contact
                  :name="contact.name"
                  :phone="contact.phone"
                  :ownername="contact.ownerName"
                  :email="contact.email"
                  :isFavorite="contact.isFavorite"
                  @update-favorite="
                     contact.isFavorite = onUpdateFavorite($event, contact.phone)
                  "
               ></Contact>
            </div>
         </div>
      </div>
   </div>
</template>

<script setup>
import { reactive, ref } from "vue";
import Contact from "./components/Contact.vue";
import AddContact from "./components/AddContact.vue";
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
]);

function onUpdateFavorite(oldValueFromChildComponent, phoneNumberFromParent) {
   console.log(oldValueFromChildComponent);
   return !oldValueFromChildComponent.isFavorite;
}
</script>

<style></style>
