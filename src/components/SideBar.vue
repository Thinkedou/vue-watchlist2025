<script setup>

const props = defineProps({
    episodeTitle:{
        type:String,
        default:"Merci de séléctionner un épisode"
    }
})

</script>
<template>
    <section class="sidebar">
        <ul>
            <li>Ici c'est fixe</li>
            <li>Un lien de nav 1</li>
            <li>Un lien de nav 2</li>
        </ul>
        <span>▶ {{ episodeTitle }}</span>
    </section>
</template>

<style scoped>
</style>