<template>
    <div class="contentId">
        <Intro :type="type" :currentMovie="getItemId" v-if="getItemId"/>
    </div>
</template>

<script setup>
    import Intro from './Intro.vue'
    import { useItemById } from '@/store/itemById'
    import { computed, onMounted } from 'vue'
    import { useRoute } from 'vue-router'
    const props = defineProps(['type'])

    const itemByIdStore  = useItemById()
    const route = useRoute()


    onMounted(() => {
    
        itemByIdStore.getItemById({type: props.type, id: route.params.id})
    })

    const getItemId = computed(() => itemByIdStore.movie)

</script>

<style lang="scss" scoped>

</style>