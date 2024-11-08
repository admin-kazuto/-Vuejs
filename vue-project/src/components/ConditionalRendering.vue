<template>
    <div v-if="!isLogin" class="login-container">
        <h2>Login</h2>
        <form v-on:submit="check" action="" method="post">
            <input type="text" placeholder="Username" name="username" required>
            <input type="password" placeholder="Password" name="password" required>
            <button type="submit">Login</button>
            <a href="#" class="forgot-password">Forgot Password?</a>
        </form>
    </div>
    <div v-else>
        <p>Chào mừng {{user.username}} đã tới</p>
        <button @click="logout">Đăng xuất</button>
    </div>
</template>

<script setup>
import { ref } from 'vue';
let isLogin = ref(false);
const user = {
    username: "admin",
    password: "123"
}

const check = (e) => {
    e.preventDefault();
    const username = document.getElementsByName("username")[0]
    const password = document.getElementsByName("password")[0]

    if(username.value ===user.username && password.value === user.password){
        alert("đăng nhập thành công")
        isLogin.value = true
    } else {
        alert("sai tài khoản")
    }
}

const logout = ()=> {
    isLogin.value = false
    alert("bạn đã đăng xuất")
}

</script>

<style scoped>
/* Reset mặc định */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Toàn trang */
body {
    font-family: Arial, sans-serif;
    background-color: #f2f2f2;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

/* Hộp form đăng nhập */
.login-container {
    width: 100%;
    max-width: 400px;
    padding: 2rem;
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    text-align: center;
}

.login-container h2 {
    margin-bottom: 1rem;
    font-size: 1.5rem;
    color: #333;
}

/* Các trường input */
.login-container input[type="text"],
.login-container input[type="password"] {
    width: 100%;
    padding: 10px;
    margin: 0.5rem 0;
    border: 1px solid #ccc;
    border-radius: 4px;
}

/* Nút đăng nhập */
.login-container button {
    width: 100%;
    padding: 10px;
    margin-top: 1rem;
    background-color: #4CAF50;
    color: #fff;
    border: none;
    border-radius: 4px;
    font-size: 1rem;
    cursor: pointer;
    transition: background-color 0.3s;
}

.login-container button:hover {
    background-color: #45a049;
}

/* Liên kết quên mật khẩu */
.login-container .forgot-password {
    display: block;
    margin-top: 1rem;
    font-size: 0.9rem;
    color: #555;
    text-decoration: none;
}

.login-container .forgot-password:hover {
    color: #333;
}
</style>