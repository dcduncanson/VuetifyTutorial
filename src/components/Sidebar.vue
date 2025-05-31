<script setup>
  import {defineEmits} from 'vue';

  const emit = defineEmits(['selectColor']);

  const selectColor = (isColor) => {
    emit('selectColor', isColor);
  };
</script>
<template>
  <v-navigation-drawer
  expand-on-hover
  rail
  >
    <v-list>
      <v-list-item
        prepend-avatar="https://mediaproxy.salon.com/width/1200/https://media2.salon.com/2015/07/paula_deen2.jpg"
        title="Paula Deen"
        subtitle="paulaskitchen@gmail.com"
        >
      </v-list-item>

      <v-divider></v-divider>

      <v-list density="compact" nav>
        <v-list-item
            prepend-icon="mdi-image"
            title="Color Images"
            value="color"
            @click="selectColor(true)"
        />
        <v-list-item
            prepend-icon="mdi-image-outline"
            title="Black & White Images"
            value="bw"
            @click="selectColor(false)"
        />
      </v-list>
    </v-list>
  </v-navigation-drawer>
</template>