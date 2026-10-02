<template>
  <div class="login-wrapper">
    <div class="login-card">
      
      <div class="left">
        <h2>Sign In</h2>

        <form @submit.prevent="handleLogin">
          <input 
            type="email" 
            placeholder="Email" 
            v-model="email" 
            required 
          />

          <input 
            type="password" 
            placeholder="Password" 
            v-model="password" 
            required 
          />

          <select v-model="level">
            <option disabled value="">Level</option>
            <option value="admin">Admin</option>
            <option value="kasir">Kasir</option>
          </select>

          <small class="forgot">Lupa Password?</small>

          <div class="btn-group">
            <button type="button" class="btn-daftar">Daftar</button>
            <button type="submit" class="btn-login">Log in</button>
          </div>
        </form>
      </div>

      <div class="right">
        <img src="@/assets/login-illustration.png" alt="Login Image" />
      </div>

    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const email = ref('')
const password = ref('')
const level = ref('')

const handleLogin = () => {
  console.log({
    email: email.value,
    password: password.value,
    level: level.value
  })
}
</script>

<style scoped>
.login-wrapper {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(to bottom, #a8cbdc, #cfe3ec);
}

.login-card {
  width: 800px;
  background: white;
  display: flex;
  padding: 40px;
  border-radius: 10px;
  box-shadow: 0 5px 20px rgba(0,0,0,0.1);
}

.left {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.left h2 {
  margin-bottom: 20px;
}

input, select {
  width: 100%;
  padding: 10px;
  margin-bottom: 15px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

.forgot {
  font-size: 12px;
  color: gray;
  margin-bottom: 15px;
  cursor: pointer;
}

.btn-group {
  display: flex;
  gap: 10px;
}

.btn-daftar {
  padding: 8px 15px;
  background: #eee;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.btn-login {
  padding: 8px 20px;
  background: #28a745;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.right {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.right img {
  width: 250px;
}
</style>