<template>
<div id="hook">

    <input type="text" placeholder="search" v-model="searchTerm">
    <h2>{{ title }}</h2> <hr>
    <div v-for="post in searchValue" :key="post.id">
            <h1>{{post.id}}</h1>
            <h5>{{post.title}}</h5>
            <p>{{post.body | snippet}}</p>
            <hr>
    </div>
  
</div>
    
</template>

<script>
import axios from 'axios'

export default {
    name:'hook',
    data(){
        return{
            title:'Axious Part :)',
            posts:[],
            searchTerm:''
          
        }
        
    },
    methods:{

    },
    computed:{
        searchValue(){
            return this.posts.filter(post=>{
                return post.title.match(this.searchTerm)
            })
        }
    },
    mounted(){
        axios.get('https://jsonplaceholder.typicode.com/posts')
        .then(Response=>{
            // console.log(Response)
            this.posts = Response.data
        })
        .catch(error=>{
            console.log(error)
        })
    }
    
    
    
}
</script>


<style scoped>
h2{
    text-align: center;
    color:red;

}
</style>