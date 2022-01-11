<template>
    <header>
        <div class="logo">
            <img src="../assets/netflix.jpg" alt="">
        </div>
    </header>
</template>

<script>
export default {
    name: "App",
    components: {
        
    },
};
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';
.logo{
    padding-top: 5px;
    img{
        width: 150px;
        align-items: center;
    }
}
header{
    background-color: $color_header;
}
</style>