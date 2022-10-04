<template>
    <div>
        <AppHeader />
        <AppMain />
    </div>
</template>

<script>
import AppHeader from "./AppHeader.vue";
import AppMain from "./AppMain.vue";
export default {
    name: "App",
    components: {
        AppHeader,
        AppMain,
    },
    data() {
        return {};
    },
};
</script>

<style lang="scss" scoped></style>
