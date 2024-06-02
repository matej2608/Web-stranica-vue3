<template>
    <img class="logo" src="../assets/staripodrum.jpg">
    <h1>Login</h1>
    <div class="login">
        <input type="text" v-model="email" placeholder="Enter Email" />
        <input type="password" v-model="password" placeholder="Enter Password" />
        <button v-on:click="login">Login</button>
        <p>
            <router-link to="/sign-up">Sign up</router-link>
        </p>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'Login',
    data()
    {
        return{
        email:'',
        password:''

    }
    },

    methods:{
        async login()
        {
            let result = await axios.get(
                `http://localhost:4000/users?email=${this.email}&password=${this.password}`
            )
        console.warn(this.email,this.password)
        }
    }

};


</script>