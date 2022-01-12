<template>
    <main>
        <MovieCard v-for="movie in MovieList" :key="movie.id" />
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
        MovieList: Array
    }
}
</script>