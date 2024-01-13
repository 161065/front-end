<template>
    <div class="sign-in-container">
    <form @submit.prevent="submitForm">
        <div>
        <input v-model="username" type="text" placeholder="Username" required class="input-field">
        <input v-model="password" type="password" placeholder="Password" required class="input-field">
        </div>

    <button type="submit" @click="signInAsEmployer" class="sign-in-button">Sign in as Employer</button>
    <span> OR </span>
    <button type="submit" @click="signInAsEmployee" class="sign-in-button">Sign in as Employee</button>
    </form>
    <p>Dont have an account? Sign up for free</p>
    <button @click="toggleSignUpToggle" class="toggle-button">  
    {{ showSignUpToggle ? 'Already have an account.' : 'Sign up' }}
    </button>
    <SignUpToggle v-if="showSignUpToggle" class="lower" />
    </div>
   </template>
   
   <script>
   import axios from 'axios'
   import { useRouter } from 'vue-router'
   import SignUpToggle from './SignUpToggle.vue'
   
   export default {
    components: {
    SignUpToggle
    },
    data() {
    return {
    username: '',
    password: '',
    showSignUpToggle: false
    }
    },
    methods: {
    toggleSignUpToggle() {
    this.showSignUpToggle = !this.showSignUpToggle
    },
    signInAsEmployer() {
    axios.post('/api/signin', {
    username: this.username,
    password: this.password,
    role: 'employer'
    })
    .then(response => {
    // handle success
    const router = useRouter()
    router.push({ name: 'Employer' })
    })
    .catch(error => {
    // handle error
    console.log(error.response)
    })
    },
    signInAsEmployee() {
    axios.post('/api/signin', {
    username: this.username,
    password: this.password,
    role: 'employee'
    })
    .then(response => {
    // handle success
    const router = useRouter()
    router.push({ name: 'Employee' })
    })
    .catch(error => {
    // handle error
    console.log(error.response)
    })
    }
    }
   }
   </script>
   
   <style scoped>
   .sign-in-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
   }
   
   .input-field {
    margin-bottom: 10px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-size: 1em;
   }
   
   .input-field:focus {
    border-color: #007bff;
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
   
   .toggle-button {
    margin-top: 20px;
    padding: 10px 20px;
    font-size: 1em;
    color: #007bff;
    background-color: transparent;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: color 0.3s ease;
   }
   
   .toggle-button:hover {
    color: #0056b3;
   }
   
   .lower {
    margin-top: 20px;
   }
   </style>