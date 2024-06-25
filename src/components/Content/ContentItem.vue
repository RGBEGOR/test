<template>
    <div class="content__list-item">
        <img v-lazy="fullImg + item.poster_path" alt="" class="content__list-img">
        <h3 class="content__list-name">
            {{ item.title || item.name }}
        </h3>
    </div>
</template>

<script setup>
    import { miniImg, fullImg } from "@/url";
    const props = defineProps(['item'])
</script>

<style lang="scss" scoped>

</style>