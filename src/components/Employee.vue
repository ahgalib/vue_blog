<template>
    <h3>Hello Galib you are a employee</h3>
    <ul>
        <li>Job : {{this.employee.Job}}</li>
        <li>Hobby : {{this.employee.hobby}}</li>
    </ul>
</template>

<script>
export default{
    name:"Employee",
    data: function(){
        return {
            employee:{
                name:"AH Galib",
                Job : "Software Engineer",
                hobby: "watching match"
            }
        }
    }
}
</script>