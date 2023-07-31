<template>
    <button @click="getPosts">Show Posts</button>

    <div v-if="posts.length === 0">No posts</div>

    <div class="container">
        <div class="div" v-for="p in posts" :key="p.id">
            <h3 class="title">{{ p.title }}</h3>
            <p class="body">{{ p.body }}</p>
        </div>

    </div>
</template>

<script setup>  

import { onMounted, ref } from 'vue';

const posts = ref([])

const getPosts = async () => {
    const response = await fetch('https://jsonplaceholder.typicode.com/posts')
    const data = await response.json()
    posts.value = data
    console.log(posts.value)
}   


// useEffect hook equivalent in Vue 3   
onMounted(() => {
    getPosts()
})  

</script>

<style scoped>
.container {
    display: flex;
    flex-wrap: wrap;    
    justify-content: center;
    column-gap: 30px;
    row-gap: 30px;
}

.div {
    border: 1px solid indianred;
    width: 375px;
    height: 375px;
   display: flex;
   flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    border-radius: 20px;
    
}

.title {
    background-color: indianred;
    border-radius: 20px 20px 0 0;
    color: rgb(255, 255, 255);
    font-size: 20px;
    padding: 30px;
    width: 100%;
    height: 100px;
    /* text-align: center;  */
    display: flex;
    align-items: center;
    justify-content: flex-start;
    font-family: 'Roboto', sans-serif;
    
}

.body {
    font-size: 20px;
    padding: 30px;
    /* roboto */
    font-family: 'Roboto', sans-serif;
}
</style>
