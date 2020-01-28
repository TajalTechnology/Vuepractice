<template>


    <div >
        <hr>
        This is from all friends

    <div v-for="(f, index) in friends" :key="index">
        <span @click="unfriend(f.name)">{{f.name}}</span>
       <!-- <span>{{f.online}}</span>-->



    </div>
        <hr>
    </div>



</template>

<script>
    export default {
        name: "AllFriends",
        props:['friends'],
        data(){
            return{
            /*    friends:[
                    {name:'Tajal Islam', online:true},
                    {name:'Sopnil Islam', online:false},
                    {name:'Tajal Islam', online:true},
                    {name:'Sopnil Islam', online:false}
                ]*/
            }
        },
        methods:{
            unfriend(name){
                this.$emit('delete',{ name })

            }

        }
    }
</script>

<style scoped>

</style>