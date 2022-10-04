<template>
    <section class="card">
        <div class="card" style="width: 18rem">
            <!-- <img src="..." class="card-img-top" alt="..." /> -->
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
