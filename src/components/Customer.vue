<template>
<h3>Hello Customer {{name}}</h3>
<h3>Hello Customer Age {{age}}</h3>
<h3>Hello Customer hobby {{hobby}}</h3>
</template>

<script>
export default{
    name:'Customer',
    props : {
        name:{type:String,required:true},
        age:{type:String,required:true},
        hobby:{type:String,required:true}
    }
}

</script>

<style>

</style>