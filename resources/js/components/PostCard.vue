<template>
    <section>
        <div class="card mx-0">
            <img
                :src="post.image"
                class="card-img-top img-fluid"
                :alt="post.image"
            />
            <div class="card-body">
                <h5 class="card-title">{{ post.title }}</h5>
                <p class="card-text">{{ post.content }}</p>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: "PostCard",
    props: {
        post: Object,
    },
};
</script>

<style lang="scss" scoped></style>
