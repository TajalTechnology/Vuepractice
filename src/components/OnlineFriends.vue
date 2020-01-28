<template>
    <div> This is from online friends

    <div v-for="(f, index) in friends" :key="index">
        <span v-if="f.online">{{f.name}}</span> <br>




    </div>
    </div>

</template>

<script>
    export default {
        name: "OnlineFriends",
        props:['friends'],
        data(){
            return{
             /*   friends:[
                    {name:'Tajal Islam', online:true},
                    {name:'Sopnil Islam', online:false},
                    {name:'Tajal Islam', online:true},
                    {name:'Sopnil Islam', online:false}
                ]*/
            }
        }
    }
</script>

<style scoped>
    div{
        font-size: 20px;
        color: aquamarine;
    }

</style>