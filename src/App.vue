<template>
  <div id="app">
    <!--<component :is="NavBar.vue"></component>-->

    <img alt="Vue logo" src="./assets/Tajal.jpg">
    <HelloWorld msg="Welcome to Your Vue.js App"/>

    <hr>
    <Blogs></Blogs>
    <hr>
    <AllFriends  :friends="friends" @delete="deleteFriend" ></AllFriends>

    <OnlineFriends :friends="friends"></OnlineFriends>
    <NavBar></NavBar>


  </div>

</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import AllFriends from './components/AllFriends.vue'
import NavBar from './components/NavBar.vue'
import OnlineFriends from './components/OnlineFriends.vue'
import Blogs from './components/Blogs.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Blogs,
    AllFriends,
    NavBar,
    OnlineFriends
  },
  data (){
    return{
      title:'This is testing purpose',
      currentComponent: 'NavBar',
      friends:[
                    {name:'Tajal Islam', online:true},
                    {name:'Sabina Islam', online:false},
                    {name:'Jahid Islam', online:true},
                    {name:'Sopnil Islam', online:false}
                ]
    }
  },
  methods:{
    deleteFriend(payload){
      // eslint-disable-next-line no-console
      console.log(payload)
      this.friends= this.friends.filter( friend =>{
        return friend.name !==payload.name
      })

    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
  img{
    height: 300px;
    width: 300px;
  }
</style>
