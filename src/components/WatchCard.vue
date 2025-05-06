<script setup>
import {computed} from 'vue'
const props = defineProps({
    title:{
        type:String,
        default:'Titre par défaut'
    },
    series:String,
    season:Number,
    episode:Number,
    bgColor:String
})
const emits = defineEmits(["onSelectedEpisode"])
const displayEpisodeNotation = computed(()=>{
    return 'E'+(props.episode<10?'0'+props.episode:props.episode)
})
const displaySeasonNotation = computed(()=>{
    return 'S'+(props.season<10?'0'+props.season:props.season)
})

const continueEpisode = ()=>{
    console.warn('📣', "hey on m'a cliqué dessus")
    emits("onSelectedEpisode",props.title)
}

</script>

<template>
    <div class="watch-card">
        <div class="course-preview" :style="{backgroundColor:bgColor}">
            <h6>Season {{season}} </h6>
            <h2>{{series}}</h2>
        </div>
        <div class="course-info">
            <h6>ep: {{displaySeasonNotation}}{{displayEpisodeNotation}}</h6>
            <h2>{{title}}</h2>
            <button :style="{backgroundColor:bgColor}" class="btn" @click="continueEpisode">Continue</button>
        </div>
    </div>
</template>


<style scoped>
</style>