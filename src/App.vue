<script setup>
import Sidebar from "@/components/Sidebar.vue";
import Gallery from "@/components/Gallery.vue";
import {ref} from "vue";

const isWithColor = ref(true);

const onSelectColor = (isColor) => {
  isWithColor.value = isColor;
};
</script>

<template>
  <v-app>
    <!-- Sidebar-->
    <Sidebar @selectColor="onSelectColor"/>
    <v-main>
      <!-- Cards -->
      <Gallery :isWithColor="isWithColor" />
    </v-main>
  </v-app>
</template>
