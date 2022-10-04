<template>
    <section id="main" class="container">
        <main>
            <div class="block-spinner" v-if="isLoading">
                <div class="spinner-border text-primary" role="status">
                    <span class="sr-only">Loading...</span>
                </div>
            </div>
            <div v-else>
                <div v-if="posts.length">
                    <h1>Posts</h1>
                    <div>
                        <PostCard
                            v-for="post in posts"
                            :key="post.id"
                            :post="post"
                        />
                    </div>
                </div>
                <div v-else>
                    <h1>Nessun post disponibile</h1>
                </div>
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
            isLoading: false,
        };
    },
    methods: {
        fetchPosts() {
            this.isLoading = true;
            Axios.get("http://127.0.0.1:8000/api/posts")
                .then((res) => {
                    this.posts = res.data.posts;
                })
                .catch((err) => {
                    console.log("Errore nel fetch dei dati!");
                })
                .then(() => {
                    console.log("Tutto appost");
                    this.isLoading = false;
                });
        },
    },
    mounted() {
        this.fetchPosts();
    },
};
</script>

<style lang="scss" scoped>
.block-spinner {
    position: fixed;

    top: 0;
    bottom: 0;
    right: 0;
    left: 0;

    background-color: transparent;
    filter: opacity(0.2);

    display: flex;
    align-items: center;
    justify-content: center;

    .spinner-border {
        width: 300px;
        height: 300px;
    }
}
</style>
