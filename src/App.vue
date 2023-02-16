<script setup>
import { ref } from "vue";
import Menu from "./components/Menu.vue";
import Content from "./components/Content.vue";

const isOpen1 = ref(true);
const isOpen2 = ref(false);
const isOpen3 = ref(false);
const isOpen4 = ref(false);

function openContent(num) {
  closeAll();
  switch (num) {
    case 1:
      isOpen1.value = true;
      break;
    case 2:
      isOpen2.value = true;
      break;
    case 3:
      isOpen3.value = true;
      break;
    case 4:
      isOpen4.value = true;
      break;
  }
}

function closeAll() {
  isOpen1.value = false;
  isOpen2.value = false;
  isOpen3.value = false;
  isOpen4.value = false;
}
</script>

<template>
  <v-container class="main-container">
    <v-row class="nav-row">
      <div class="left-col">
        <Menu
          title="Home"
          @click="openContent(1)"
          :class="{ active: isOpen1 }"
          :isActive="isOpen1"
        />
        <Menu
          title="Map"
          @click="openContent(2)"
          :class="{ active: isOpen2 }"
          :isActive="isOpen2"
        />
        <Menu
          title="Control"
          @click="openContent(3)"
          :class="{ active: isOpen3 }"
          :isActive="isOpen3"
        />
        <Menu
          title="Contact"
          @click="openContent(4)"
          :class="{ active: isOpen4 }"
          :isActive="isOpen4"
        />
      </div>
      <div class="center-col"></div>
      <div class="right-col">
        <Content content="ホーム" v-show="isOpen1" />
        <Content content="マップ" v-show="isOpen2" />
        <Content content="コントロール" v-show="isOpen3" />
        <Content content="コンタクト" v-show="isOpen4" />
      </div>
    </v-row>
  </v-container>
</template>

<style>
.main-container {
  min-width: 100vw;
  min-height: 100vh;
  width: 100vw;
  height: 100vh;
  background-image: url(./assets/bg-img.jpg);
  background-size: cover;
  display: flex;
  align-items: center;
  justify-content: center;
}

.nav-row {
  display: flex;
  justify-content: center;
  margin: 1em;
  height: 90vh;
}

.left-col {
  width: 30vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin: 1em;
  transform: perspective(600px) rotateY(10deg);
}

.center-col {
  width: 10vw;
}

.right-col {
  width: 50vw;
  margin: 1em;
  transform: perspective(1200px) rotateY(-10deg);
}


</style>
