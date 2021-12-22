<template>
    <div>
        <h3>Posts:</h3>
        <hr>
        <input type="text" v-model="searchTerm" placeholder="Search">
        <div v-for="post in filterSearch" :key="post.id">
            <h4 id="title">{{post.title}}</h4>
            <p>{{post.body | snippet}}</p>
        </div>

    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'Posts',
    data() {
        return {
            posts: [],
            searchTerm: ''
        }
    },
    computed: {
        filterSearch() {
            return this.posts.filter(post => {
                return post.title.match(this.searchTerm)
            })
        }
    },
    methods: {

    },
    // lifecycle hook
    created() {
        axios.get('https://jsonplaceholder.typicode.com/posts')
        .then(res => {
            // console.log(res.data)
            this.posts = res.data
        })
        .catch(err => {
            console.log(err)
        })
    }
}
</script>

<style>
#title {
    color: rgb(0, 47, 255);
}
</style>