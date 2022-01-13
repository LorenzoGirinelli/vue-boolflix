<template>
    <div class="movie">
        <div class="container">
            <ul>
                <div v-if="details.poster_path !== null" class="poster">
                    <img :src="'https://image.tmdb.org/t/p/w342' + details.poster_path" :alt="details.name">
                </div>
                <div>Titolo: {{details.title}} </div>
                <div v-if="details.original_title">
                    Titolo originale: {{details.original_title}} 
                </div>
                <div v-else>Titolo originale: {{details.original_name}}</div>
                <div>
                    Lingua: {{details.original_language}}
                </div>
                <div>
                    Voto: {{details.vote_average}}
                </div>
                <div v-if="details.original_language === 'it'  || details.original_language === 'en' || details.original_language === 'pt'"  class="flag">
                    <img :src= "require( '../assets/img/' + details.original_language + '.png')" >
                </div>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: "MovieCard",
    props: {
        details: Object
    }
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';
.movie {
    margin: 10px;
    border: 1px solid black;
    width: calc( (100% / 10) - 10px);
    text-align: center;
    img {
        width: 20px;
    }
    .poster{
        img{
            width: 220px;
        }
    }
}
</style>