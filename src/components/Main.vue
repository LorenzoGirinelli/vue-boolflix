<template>
    <main>
        <h2 class="movielist">Film</h2>
        <div class="movielist">
            <MovieCard v-for="movie in MovieList" :key="movie.id" :details="movie" />
        </div>
        <h2 class="movielist">Serie</h2>
        <div class="movielist">
            <MovieCard v-for="serietv in seriesList" :key="serietv.id" :details="serietv" />
        </div>
    </main>
</template>

<script>
import MovieCard from "./MovieCard.vue";
export default {
    name: "Main",
    components: {
        MovieCard
    },
    props: {
        MovieList: Array,
        seriesList: Array
    }
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';
</style>