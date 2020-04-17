<template>
    <div class="auth-container">
        <h1 class="auth-title">To do list</h1>
        <form class="auth-form" onsubmit="return false">
            <div class="auth-hor">
                <label for='name'>Логин</label>
                <input type="text" class="auth-name" v-model='name' name='name'>
            </div>
            <div class="auth-hor">
                <label for='name'>Пароль</label>
                <input type="password" class="auth-pass" v-model='pass' name='pass'>
            </div>
            <button v-on:click = 'logIn'>Войти</button>
        </form>
        
    </div>
</template>

<script>
export default {
    data(){
        return{
            name: '',
            pass: '',
            gName: '',
            
        }
    },methods: {
        logIn: function(){
            this.$emit('event');
        }
    },
}
</script>

<style>
*{
    font-family: Montserrat;
    font-size: 24px;
}
body{
    margin: 0;
    background: #E5E5E5;
}
.auth-title{

    font-family: Playfair Display;
    font-size: 120px;
    color: #C6B3A6;
}
.auth-container{
    /* height: 100vh; */
    display: flex;
    text-align: center;
    justify-content: center;
    flex-direction: column;
    height: 100vh;
}
.auth-form{
    display: flex;
    flex-direction: column;
    /* width: 500px; */
    margin: 0 auto;
    justify-content: center;
    align-items: flex-end;
}
.auth-hor{
    display: flex;
    align-items: center;
}
.auth-form label{
    margin-right: 57px;
}
.auth-form input{
    width: 419px;
    background: #2B2B2B;
    opacity: 0.4;
    border-radius: 7px;
    height: 70px;
    margin: 0 auto;
}
.auth-form button{
    width: 361px;
    height: 75px;
    border: 1px solid #2B2B2B;
    box-sizing: border-box;
    border-radius: 5px;
    margin: 0 auto;
    font-family: Montserrat;
    font-size: 24px;
    color: #2B2B2B;
    margin-top: 80px;
}
</style>

