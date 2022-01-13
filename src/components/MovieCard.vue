<template>
    <div class="movie">
        <div>Titolo: {{details.title}} </div>
        <div>
            Titolo originale: {{details.original_title}} 
        </div>
        <div>
            Lingua: {{details.original_language}}
            </div>
        <div>
            Voto: {{details.vote_average}}
        </div>
        <div v-if="details.original_language === 'it'  || details.original_language === 'en' || details.original_language === 'pt'"  class="flag">
             <img :src= "require( '../assets/img/' + details.original_language + '.png')" >
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
    img {
        width: 20px;
    }
}
</style>