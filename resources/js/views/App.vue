<template>
    <div>
        <h1>Post Lists</h1>
        <ul>
            <li v-for="post in posts" :key="post.slug">
                {{post.title}}
            </li>
        </ul>
    </div>
</template>

<script>
import Axios from 'axios'
import { createDecipheriv } from 'crypto'

export default {
    name: 'App',
    data() {
        posts: []
    },
    created() {
        axios.get('http://127.0.0.1:8001/api/posts')
        .then((response) => {
            console.log(response.data);
        })
        .catch()
    }
};
</script>

<style>

</style>