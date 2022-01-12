<template>
    <div class="movie">
        <div>Titolo: [titlo]</div>
        <div>Titolo originale: [titlo originale]</div>
        <div>Lingua: [lingua]</div>
        <div>Voto: [voto]</div>
    </div>
</template>

<script>
export default {
    name: "MovieCard",
    props: Object
}
</script>

<style scoped>
.movie {
    margin: 10px;
    border: 1px solid black;
}
</style>