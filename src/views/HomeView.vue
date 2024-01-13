<template margin-bottom>
 <h1 >Welcome to job finders.com</h1>
  <div class="home-container">
    <p>Sign in to find a job now!</p>
  <button @click="showSignIn = !showSignIn" class="sign-in-button">
  {{ showSignIn ? 'Hide Sign In / Sign Up' : 'Sign In / Sign Up' }}
  </button>
  <SignIn v-if="showSignIn" class="lower" />
  </div>
 </template>
 
 <script>
 import SignIn from '../components/SignIn.vue'
 
 export default {
  components: {
  SignIn
  },
  data() {
  return {
  showSignIn: false
  }
  }
 }
 </script>
 
 <style scoped>
 .home-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  margin-top: -100px;
 }
 
 .sign-in-button {
  margin-top: 20px;
  padding: 10px 20px;
  font-size: 1em;
  color: #fff;
  background-color: #007bff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
 }
 
 .sign-in-button:hover {
  background-color: #0056b3;
 }
 
 .lower {
  margin-top: 20px;
 }
 </style>