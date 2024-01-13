



 <template>
 <div class="header-container">
  <img class="logo" src="/src/assets/logo.jpg" alt="Logo">
 <div class="header-nav">
 <a href="#" @click="goToHome" class="nav-link">Home</a>
 <a href="/about" class="nav-link">About</a>
 </div>
 </div>
 <hr>
</template>

<script>
export default {
 methods: {
 goToHome() {
 this.$router.push('/home');
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

.logo {
 height: 80px;
 width: 150px;
}

.header-nav {
 display: flex;
}

.header-nav a {
 margin-left: 20px;
 padding: 10px 20px;
 background-color: #007bff;
 color: #fff;
 border-radius: 5px;
 text-decoration: none;
 transition: background-color 0.3s ease;
}

.header-nav a:hover {
 background-color: #0056b3;
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