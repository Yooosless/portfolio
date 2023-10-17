<script setup>

import ContactsCard from './components/contactscard.vue';

import MainCard from './components/maincard.vue';
import NavbarCard from './components/NavbarCard.vue';
import ProjectsCard from './components/projectscard.vue';

</script>

<template>
  
  <div  class="app-container">
    <NavbarCard />
    <MainCard />
    <ProjectsCard />
    <ContactsCard />
  </div>
</template>

<style scoped>

 /* .app-container{
  background-color: rgb(25, 19, 31);
 } */
</style>
