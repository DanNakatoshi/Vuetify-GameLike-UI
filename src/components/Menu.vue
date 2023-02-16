<script setup>
import { defineProps } from "vue";

const props = defineProps({
  title: String,
  isActive: Boolean,
});
</script>

<template>
  <v-btn class="my-4 ma-4 btn" :class="isActive ? 'active' : 'glass'">
    {{ props.title }}
  </v-btn>
</template>

<style scoped>
.glass {
  background: rgba(48, 29, 183, 0.4);
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
  backdrop-filter: blur(7px);
  -webkit-backdrop-filter: blur(7px);
  border-radius: 10px;
  border: 1px solid rgba(255, 255, 255, 0.18);
}

.btn {
  font-size: 32px;
  color: white;
  min-height: 120px;
}

.active {
  scale: 1.1;
  background: rgba(142, 162, 16, 0.5);
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
  backdrop-filter: blur(15px);
  -webkit-backdrop-filter: blur(15px);
  border-radius: 10px;
  border: 1px solid rgba(255, 255, 255, 0.18);
}
</style>
