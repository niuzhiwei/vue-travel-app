<template>
   <div>
      <home-header></home-header>
      <home-swiper :list="swiperList"></home-swiper>
      <home-icons :list="iconList"></home-icons>
      <home-hot :list="hotList"></home-hot>
      <home-recommend :list="recommendList"></home-recommend>
      <home-weekend :list="weekendList"></home-weekend>
   </div>
</template>
<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeHot from './components/Hot'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
import {mapState} from 'vuex'
export default {
    components:{HomeHeader,HomeSwiper,HomeIcons,HomeRecommend,HomeWeekend,HomeHot},
    name:'Home',
    methods:{
        getHomeInfo(){
            axios.get('/api/index.json?city=' + this.city)
            .then(this.getHomeInfoSucc)
        },
        getHomeInfoSucc(res){
            res = res.data
            if(res.ret && res.data){
                this.swiperList = res.data.swiperList
                this.iconList = res.data.iconList
                this.recommendList = res.data.recommendList
                this.weekendList = res.data.weekendList
                this.hotList = res.data.hotList
            }
        }
    },
    mounted(){
        this.getHomeInfo()
        this.lastCity = this.city
    },
    data(){
        return{
            swiperList:[],
            iconList:[],
            hotList:[],
            recommendList:[],
            weekendList:[],
            lastCity:''
        }
    },
    computed:{
        ...mapState(['city']),
    },
    activated(){
        if(this.lastCity !== this.city){
            this.lastCity = this.city
            this.getHomeInfo()
        }
    }
}
</script>
<style>

</style>


