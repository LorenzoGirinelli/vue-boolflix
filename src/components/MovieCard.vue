<template>
    <div class="movie">
        <div>
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
                    Voto: {{star()}}
                    <span v-for="n in 5" :key="n">
                        <i class="fas fa-star" v-if="n <= star()"></i>
                        <i class="far fa-star" v-else></i>
                    </span>
                </div>
                <div v-if="details.original_language === 'it'  || details.original_language === 'en' || details.original_language === 'pt'"  class="flag">
                    <img :src= "require( '../assets/img/' + details.original_language + '.png')" >
                </div>
                <div v-else>
                    Lingua: {{details.original_language}}
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
    },
    methods:{
        star: function () {
            return Math.ceil(this.details.vote_average / 2);
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';
.movie {
    margin: 15px;
    border: 1px solid black;
    width: calc( (100% / 6) - 10px);
    text-align: center;
    img {
        width: 20px;
    }
    .poster{
        img{
            width: 200px;
        }
    }
}
@media screen and (min-width: 400px) {
    .movie{
        width:calc((100% / 2) - 20px)
    }
}
@media screen and (min-width: 576px) {
    .movie{
        width:calc((100% / 3) - 20px)
    }
}
@media screen and (min-width: 780px){
    .movie{
        width: calc((100% / 4) - 20px)
    }
};
@media screen and (min-width: 1025px){
    .movie{
        width: calc((100% / 5) - 20px)
    }
};
@media screen and (min-width: 1317px){
    .movie{
        width: calc((100% / 6) - 10px)
    }
}
</style>

