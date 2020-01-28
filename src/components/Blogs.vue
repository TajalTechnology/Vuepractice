<template>
    <div class="blogs">
        <h2>{{blogTitle}}</h2>
        <input type="text" v-model="searchTerm">
        <div v-for="post in filterPosts" :key="post.id">
        {{post.title}}
            <p>{{ post.body | snippet }} </p>


        </div>
        <button @click="changeTitle"> changeTitle</button>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        name: "Blogs",
        data(){
            return {
                blogTitle:'Blogs',
                posts:[],
                searchTerm:''
            }
        },
        methods:{
            changeTitle(){
                this.blogTitle='Amazing Blog Site'
            }

        },
        computed:{
        filterPosts(){
            return this.posts.filter(post =>{
                return post.title.match(this.searchTerm)
            })
        }
        },
        beforeCreate() {
            /*alert('beforeCreate hook')*/
        },
        created() {
            axios.get('https://jsonplaceholder.typicode.com/posts/')
                .then(response =>{
                    // eslint-disable-next-line no-console
                    console.log(response)
                    this.posts=response.data
                }).catch(err =>{
                // eslint-disable-next-line no-console
                    console.log(err)
            })
        },
        beforeUpdate() {
          /*alert('beforeUpdate hook')*/

        }
    }
</script>

<style scoped>

</style>