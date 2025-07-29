<template>
   <div class="container border rounded p-2">
      <div class="text-center text-white">Add new Contact</div>
      <form @submit.prevent="addContact">
         <div class="row">
            <div class="col-4">
               <input type="text" class="form-control" v-model="contact.name" placeholder="Name">
            </div>
            <div class="col-4">
               <input type="text" class="form-control" v-model="contact.email" placeholder="Email">
            </div>
            <div class="col-4">
               <input type="text" class="form-control" v-model.number="contact.phone" placeholder="Phone">
            </div>
         </div>
         
         <div class="col-6 offset-3 p-2">
            <button type="submit" class="btn btn-secondary w-100" >Submit</button>
         </div>
      </form>
   </div>
</template>

<script setup>
import {reactive, defineEmits} from "vue";

const contact = reactive({
   name: "",
   phone: "",
   email: "",
});

function addContact() {
   emit("add-contact", {
      name: contact.name,
      phone: contact.phone, 
      email: contact.email,
   })
   console.log(contact);
   contact.email="";
   contact.name="";
   contact.phone="";
}

const emit = defineEmits(["add-contact"]);

</script>