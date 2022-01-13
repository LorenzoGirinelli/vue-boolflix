<template>
    <header>
        <!-- Logo -->
        <div class="logo">
            <img src="../assets/netflix.jpg" alt="logo Netflix">
        </div>
        <!-- Header Nav -->
        <div>
            <div class="nav">
                <div class="nav-element">
                    Home
                </div>
                <div class="nav-element">
                    Film
                </div>
                <div class="nav-element">
                    Serie tv
                </div>
                <div class="nav-element">
                    Continua a guardare
                </div>
            </div>
        </div>
        <div
        class="search-area">
            <!-- Input -->
            <input 
            v-model="usersearchText" 
            type="text" 
            placeholder="Cerca un film o una serie tv">
            <!-- Bottone -->
            <button 
            @click="$emit('searchDone', usersearchText)">
                Cerca
            </button>
        </div>
    </header>
</template>

<script>
export default {
    name: 'Header',
    data: function(){
        return{
            usersearchText: '',
        }
    }
}
</script>

<style scoped lang="scss">
header{
    font-family: Arial, Helvetica, sans-serif;
    height: 105px;
    line-height: 100px;
    background-color: #161616;
    display: flex;
    align-items: center;
    justify-content: space-between;
    .logo{
        flex-grow: 0;
        margin-left: 30px;
        display: none;
        cursor: pointer;
        img{ 
            vertical-align: middle;
            width: 200px;
            height: 100px;
        }
    }
    @media screen and (min-width: 780px) {
    .logo{
            display: inline-block;
        }
    }
    .nav{
        display: none;
        justify-content: space-between;
        color: white;
        .nav-element{
            margin: 0 20px;
            font-size: 20px;
            font-weight: bold;
            cursor: pointer;
        }
    }
    @media screen and (min-width: 1317px) {
    .nav{
            display: flex;
        }
    }
    .search-area{
        display: flex;
        input{
            text-align: center;
            margin-left: 30px;
            margin-right: 30px;
            padding: 5px 18px;
            min-width: 330px;
            min-height: 25px;
            border-radius: 10px;
            background-color: lightgrey;
            font-size: 20px;
        }
        button{
            padding: 5px 18px;
            margin-right: 20px;
            border-radius: 10px;
            background-color: lightgrey;
            cursor: pointer;
            font-size: 20px;
        }
    }
}
</style>