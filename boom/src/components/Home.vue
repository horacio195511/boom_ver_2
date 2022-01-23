<template>
    <div class="center-no-back">
        <div class="center">
            <button type="button" @click="home">Home</button>
            <button type="button" @click="login">Login</button>
            <button type="button" @click="market">Market</button>
            <button type="button" @click="learmore">Learn More</button>
        </div>
        <div class="center-no-back">
            <news-frame v-for="news in newsList" :key="news.key" :news="news">
            </news-frame>
        </div>
    </div>
</template>

<script>
import NewsFrame from './Item/NewsFrame.vue'
export default {
  components: {
      NewsFrame
    },
    name: 'Home',
    data(){
        return{
            newsList:[
                {   key:1,
                    title:'hello world', 
                    article:'this is the first article published on this site, and the website works very good'
                },
                {   key:2,
                    title:'boom',
                    article:'I am the first production machine in the world'
                },
                {   key:3,
                    title:'new feature release',
                    article:'this website has facelift using css on this wednesday'
                },
                {   key:4,
                    title:'end of trial',
                    article:'congradulation, all of the customer that spend more than 200 grand would got a free account'
                },
                {   key:5,
                    title:'boom',
                    article:'I am the first production machine in the world'
                },
                {   key:6,
                    title:'this world is very bad',
                    article:'This world is a bad place to live, the pepople are not kind at all, no one love other from inside, all of the emotion are fake, and no one respect love from others.'
                },
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

</style>