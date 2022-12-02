<template>
    <div class="container">
        <div class="row">
            <div class="col-md-5">
                <div class="card">
                    <h3>{{this.number}}</h3>
                    <div class="d-flex">
                        <button class="btn btn-info" @click="this.incr">Increment</button>
                        <button class="btn btn-danger" @click="this.decr">decrement</button>
                        <button class="btn btn-danger" @click="this.multi">decrement</button>
                    </div>
                </div>
            </div>

        </div>
    </div>

</template>

<script>
export default{
    data : function(){
        return{
           number:4
        }
    },
    methods:{
        incr:function(){
            this.number = this.number +1
        },
        decr:function(){
            this.number = this.number -1
        },
        multi:function(){
            this.number = this.number * this.number
        },
    }
}

</script>