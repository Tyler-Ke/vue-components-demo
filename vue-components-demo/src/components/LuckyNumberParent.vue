<template>
   <div class="bg-black text pt-3" :style="{ height: '100vh' }">
      <h1 class="text-center text-success">Lucky Number Generator</h1>
      <div class="container text-center bg-white">
         <slot></slot>
         <button
            @click="newVersion = !newVersion"
            class="btn btn-primary text-black m-2"
         >
            Toggle Component
         </button>
         <br />
         <button
            @click="newVersion = false"
            class="btn btn-primary text-black m-2"
         >
            Lucky Number v1
         </button>
         <button
            @click="newVersion = true"
            class="btn btn-primary text-black m-2"
         >
            Lucky Number v2
         </button>
         <br />
         <br />
         <keep-alive :include="['LuckyNumber', 'LuckyNumberV2']" exclude="">
            <component :is="currentComponent" class="border"></component>
         </keep-alive>
      </div>
   </div>
</template>

<script setup>
import { reactive, ref, computed } from "vue";
import LuckyNumber from "./LuckyNumber.vue";
import LuckyNumberV2 from "./LuckyNumberV2.vue";

const newVersion = ref(true);

const currentComponent = computed(() => {
   return newVersion.value ? LuckyNumberV2 : LuckyNumber;
});
</script>

<style></style>
