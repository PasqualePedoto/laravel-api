<template>
    <div class="mb-4 d-flex flex-row post-card">
        <figure class="m-0 h-100">
            <img
                :src="post.image"
                class="card-img-top img-fluid"
                :alt="post.image"
            />
        </figure>
        <div class="flex-grow-1">
            <div class="card-header">{{ post.title }}</div>
            <p class="card-text">{{ post.content }}</p>
            <div class="card-footer">{{ post.title }}</div>
        </div>
    </div>
</template>

<script>
export default {
    name: "PostCard",
    props: {
        post: Object,
    },
};
</script>

<style lang="scss" scoped>
.post-card {
    width: 100%;
    height: 300px;

    figure {
        width: 40%;
    }
}
</style>
