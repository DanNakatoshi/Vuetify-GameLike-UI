<script setup>
import { defineProps } from "vue";

const props = defineProps({
  content: String,
});
</script>

<template>
  <div class="content-wrapper glass">
    {{ props.content }}
  </div>
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

.content-wrapper {
  width: 100%;
  height: 100%;
  color: white;
}
</style>
