<template>
    <div class="header-container">
    <img class="logo" src="/src/assets/logo.jpg" alt="Logo">
    <div class="header-nav">
    <button @click="goToProfile" class="nav-link">Profile</button>
    <button @click="logOut" class="nav-link">Log Out</button>
    </div>
    </div>
   </template>
   
   <script>
   export default {
    methods: {
    goToProfile() {
    this.$router.push('/profile');
    },
    logOut() {
    // Add your log out logic here
    }
    }
   }
   </script>
   

   <style scoped>
   .header-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px;
    background-color: #f8f9fa;
   }
   