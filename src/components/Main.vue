<template>
    <main>
        <h2>Film</h2>
        <MovieCard v-for="movie in MovieList" :key="movie.id" :details="movie" />
        <h2>Serie</h2>
        <MovieCard v-for="serietv in seriesList" :key="serietv.id" :details="serietv" />
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