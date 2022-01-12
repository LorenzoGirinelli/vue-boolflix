<template>
    <header>
        <div class="logo">
            <img src="../assets/netflix.jpg" alt="">
            <input v-model="userSearchtext" type="text">
            <button @click="$emit('searchDone', userSearchtext)">Cerca</button>
        </div>
    </header>
</template>

<script>
export default {
    name: "Header",
    data: function () {
        return {
            userSearchtext: ''
        };
    }
        
}
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