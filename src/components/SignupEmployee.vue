<template>
   <div class="wrapper">
     <form @submit.prevent="submitForm">
      <div> <input v-model="username" type="text" placeholder="Username" required> </div>
         <div>  <input v-model="password" type="password" placeholder="Password" required> </div>
            <div>  <input v-model="rePassword" type="password" placeholder="Re-enter password" required> </div>
               <div>   <input v-model="firstName" type="text" placeholder="First name" required> </div>
                  <div>  <input v-model="lastName" type="text" placeholder="Last name" required> </div>
                     <div>  <input v-model="city" type="text" placeholder="City" required> </div>
                        <div>  <button @click="submitForm" class="sign-in-button">Confirm</button> </div>
     </form>
   </div>
   </template>
   
 
   <script>
   import axios from 'axios'
   
   export default {
    data() {
    return {
    username: '',
    password: '',
    rePassword: '',
    firstName: '',
    lastName: '',
    city: ''
    }
    },
    methods: {
    submitForm() {
    if (this.password !== this.rePassword) {
     alert('Passwords must match!')
     return
    }
    axios.post('/api/employees', {
     username: this.username,
     password: this.password,
     firstName: this.firstName,
     lastName: this.lastName,
     city: this.city
    })
    .then(response => {
     // handle success
     console.log(response.data)
    })
    .catch(error => {
     // handle error
     console.log(error.response)
    })
    }
    }
   }
   </script>

   <style>
.sign-in-button {
 margin-top: 10px;
 padding: 20px 20px;
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

.wrapper label {
    float: left;
    margin-right: 10px;
}
.wrapper div {
    margin-bottom: 0px;
}
</style>
