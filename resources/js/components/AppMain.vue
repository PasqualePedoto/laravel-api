<template>
    <section id="main" class="container">
        <main>
            <h1>Posts</h1>
            <div>
                <PostCard v-for="post in posts" :key="post.id" :post="post" />
            </div>
        </main>
    </section>
</template>

<script>
import Axios from "axios";
import PostCard from "./PostCard.vue";
export default {
    name: "AppMain",
    components: { PostCard },
    data() {
        return {
            posts: [],
        };
    },
    methods: {
        fetchPosts() {
            Axios.get("http://127.0.0.1:8000/api/posts")
                .then((res) => {
                    this.posts = res.data.posts;
                })
                .catch((err) => {
                    console.log("Errore nel fetch dei dati!");
                });
        },
    },
    mounted() {
        this.fetchPosts();
    },
};
</script>

<style></style>
