<script setup>
import { RouterView } from 'vue-router'

import Header from '../src/components/Header.vue';
import Menubar from '../src/components/Menubar.vue';
import Footer from '../src/components/Footer.vue';

</script>
<template>
  <Header></Header>
  <Menubar></Menubar>
  <RouterView></RouterView>
  
  <Footer></Footer>
   
</template>
<style scoped></style>