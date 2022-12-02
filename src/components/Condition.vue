<template>
   
    <div class="container">
        <div class="row m-4">
            <div class="col-md-12 p-4">
                <div class="d-flex m-3">
                    <h4>Login = {{this.isLogin}}</h4>
                   <div v-if="isLogin" class="bg-success p-3">
                        <p>Hello User..You are now login to our site and we are happy for it</p>
                     
                   </div>
                   <div v-if="!isLogin" class="bg-warning p-3">
                        <p>Hello Guest..Please log in to our site</p>
                       
                   </div>
                </div>
                <button v-if="isLogin" class="btn btn-danger" @click="logout()">Logout</button>
                <button v-if="!isLogin" class="btn btn-primary" @click="login()">Login</button>
            </div>
        </div>
    </div>
</template>

<script>
export default{
    name:"Condition",
    data:function(){
        return{
            isLogin :"false"
        }
    },
    methods:{
        login:function(){
            this.isLogin = true
        },
        logout:function(){
            this.isLogin = false
        }
    }
}
</script>