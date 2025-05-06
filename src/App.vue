<script setup>
import WatchCard from './components/WatchCard.vue'
import SideBar from './components/SideBar.vue'
import {userWatchList} from './assets/js/watchList.js'
import {ref} from 'vue'
const watchList = ref(userWatchList)
const currentEpisode = ref("")

const onSelectedEpisodeHandler = (data)=>{
  currentEpisode.value = data
  console.log('👂',"j'ai bien entendu l'enfant!", data)
}
</script>

<template>
  <div class="container">
    <SideBar :episodeTitle="currentEpisode"  />
    <main class="courses-container">
      <WatchCard 
        v-for="episode in watchList"
        :key="episode.title"
        :title="episode.title"
        :series="episode.series"
        :season="episode.season"
        :episode="episode.episode"
        @onSelectedEpisode="onSelectedEpisodeHandler"
      />             
    </main>
  </div>
</template>

<style scoped>

</style>
