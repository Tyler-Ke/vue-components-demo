<template>
   <div class="">
      <h1>Contact Us</h1>
      <p>Please send us an email at {{ email }}</p>
   </div>
</template>

<script>
import {ref} from "vue";

export default{
   setup() {
      const email = ref("fakeemail2@gmail.com")

      return { email };
   }
}
</script>