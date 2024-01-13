<template>
    <div class="button-container">
    <button @click="currentComponent = 'SignupEmployer'" class="sign-in-button">Sign up as employer</button>
    <span> or </span>
    <button @click="currentComponent = 'SignupEmployee'" class="sign-in-button">Sign up as employee</button>
    <component :is="currentComponent"></component>
    </div>
 </template>
 
 <script>
 import SignupEmployer from './SignupEmployer.vue'
 import SignupEmployee from './SignupEmployee.vue'
 
 export default {
  components: {
  SignupEmployer,
  SignupEmployee
  },
  data() {
  return {
  currentComponent: ''
  }
  }
 }
 </script>
 



 <style >
 .button-container {
   display: flex;
   flex-direction: column;
   align-items: center;
   justify-content: center;
 }
 .sign-in-button {
 margin-top: 10px;
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
</style>