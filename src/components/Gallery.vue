<script setup>
  import {defineProps} from 'vue';

  const p = defineProps(["isWithColor"]);
  const copyUrl = async (url) => {
    await navigator.clipboard.writeText(url)
  }
</script>

<template>
  <v-card class="mx-5 my-2 pa-3">
  <v-row>
    <v-col
      v-for="n in 200"
      cols="4"
      sm="3"
      md="2"
      lg="1"
    >
      <v-hover
        v-slot:default="{isHovering, props}"
      >
      <v-card
        :elevation="isHovering ? 12 : 2"
        :class="{ 'hovered-card': isHovering }"
        v-bind="props"
        @click="copyUrl()"
        >
          <v-img
            :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${p.isWithColor ? '' : '&grayscale'}`"
            :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${p.isWithColor ? '' : '&grayscale'}`"
            aspect-ratio="1"
            cover
          >
            <template v-slot:placeholder>
              <v-row
              class="fill-height ma-0"
              align="center"
              justify="center"
              >
              <v-progress-circular
                indeterminate
                color="grey lighten-4"
                ></v-progress-circular>
              </v-row>
            </template>
          </v-img>
      </v-card>
      </v-hover>
    </v-col>
  </v-row>
  </v-card>
</template>

<style scoped>
.hovered-card {
  border: 2px solid #1976d2;
  transition: border 0.2s;
}
</style>
