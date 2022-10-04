<template>
    <div class="card mb-4">
        <figure class="m-0">
            <img
                :src="post.image"
                class="card-img-top img-fluid"
                :alt="post.image"
            />
        </figure>
        <div class="card-body">
            <h5 class="card-title">{{ post.title }}</h5>
            <p class="card-text">{{ post.content }}</p>
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
.card {
    min-height: 300px;
    width: 300px;
    figure {
        height: 200px;

        img {
            width: 100%;
            height: 100%;
        }
    }
}
</style>
