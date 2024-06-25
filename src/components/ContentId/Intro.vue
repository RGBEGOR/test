<template>
  <div class="media">
    <img class="media__poster" v-lazy="fullImg + currentMovie.backdrop_path" alt="" />
    <div class="media__block">
      <div class="media__block-left">
        <h1 class="media__block-left-title">{{currentMovie.name || currentMovie.title}}</h1>
        <p class="media__block-left-text">
          {{ currentMovie.overview  || currentMovie.name }}
        </p>
        <p class="media__block-left-janr">
            <span>{{ getYear }}</span>
            <span>{{ getGenres }}</span>
        </p>
        <BtnMore />
      </div>

      <div class="media__block-right">
        <img v-lazy="fullImg + currentMovie.poster_path" alt="" />
      </div>
      <div class="media__block-actors">
        <h2 class="media__block-title">В главных ролях</h2>
        <div class="media__block-casts">
          <Actor :type="type" :id="currentMovie.id" :count="6" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { miniImg, fullImg } from "@/url";
import {computed} from 'vue'
const props = defineProps(["type", "currentMovie"]);




const getYear = computed(() => new Date(props.currentMovie.release_date).getFullYear() || new Date(props.currentMovie.first_air_date).getFullYear())
const getGenres = computed(() => props.currentMovie.genres.reduce((acc, item) => acc + `, ${item.name}`, ''))
</script>

<style lang="scss" scoped>
</style>