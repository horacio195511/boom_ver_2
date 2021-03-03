<template>
    <div>
        <div class="menu">
            <button type="button" @click="home">Home</button>
            <button type="button" @click="login">Login</button>
            <button type="button" @click="market">Market</button>
            <br>
            <button type="button" @click="learmore">Learn More</button>
        </div>
        <news-frame v-for="news in newsList" :key="news.key" :news="news">
        </news-frame>
    </div>
</template>

<script>
import NewsFrame from './Item/NewsFrame.vue'
export default {
  components: {
      NewsFrame
    },
    name: 'Home',
    component: {
        NewsFrame,
    },
    data(){
        return{
            newsList:[
                {key:1, title:'hello', article:'world'},
                {key:2, title:'boom', article:'the production machine'},
            ],
        }
    },
    methods:{
        login(){
            this.$emit('change-view','Login');
        },
        market(){
            this.$emit('change-view', 'Market');
        }
    }
}
</script>

<style>
.menu{
    background-image: url(../assets/BOOM_LOGO_003.png);
    background-size: contain;
    height: 458px;
    width: 646px;
}
</style>