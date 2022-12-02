<template>
    <p>{{this.name}}</p>
    <div class="container mt-4">
        <div class="row">
            <div class="col-lg-6">
                <form @submit.prevent="register()" class="form-group m-auto">
                    <input v-model="name" type="name" name="name" placeholder="enter name" class="form-group">
                    <input type="submit" name="" id="">
                </form>
            </div>
        </div>
    </div>
</template>

<script>
export default{
    name:"Form",
    data:function(){
        return{
            name:'',
        }
    },
    methods:{
        register:function(){
            console.log(this.name)
            this.name = ""
        }
    }
}
</script>