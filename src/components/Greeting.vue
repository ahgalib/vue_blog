<template>
    
    <div class="d-flex">
        <h3>Hello {{this.msg}}</h3>
        <button class="btn btn-success" @click="greeting('good morning')">Good morning</button>
        <button class="btn btn-warning"  @click="greeting('good evening')">Good evening</button>
        <button class="btn btn-info"  @click="greeting('good night')">Good night</button>
    </div>
</template>

<script>
export default{
    data:function(){
        return{
            msg:""
        }
    },
    methods:{
        greeting:function(value){
            this.msg = value
        }
    }
}
</script>