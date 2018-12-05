<template>
    <div>
      <detail-banner :sightName="sightName" :bannerImg="bannerImg" :gallaryImgs="gallaryImgs"></detail-banner>
      <detail-header></detail-header>
      <div class="content">
          <detail-list :list="list"></detail-list>
      </div>
    </div>
</template>
<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
    name:"Detail",
    components:{
        DetailBanner,
        DetailHeader,
        DetailList
    },
    data(){
        return{
            list:[],
            sightName:'',
            bannerImg:'',
            gallaryImgs:[]
        }
    },
    mounted(){
        this.getDetailInfo()
    },
    methods:{
        getDetailInfo(){
            axios.get('/api/detail/'+this.$route.params.id+'.json').then(this.handlegetDataSucc)
        },
        handlegetDataSucc(res){
           res = res.data
           if(res.ret && res.data){
               const data = res.data.data
               this.sightName = data.sightName
               this.bannerImg = data.bannerImg
               this.gallaryImgs = data.gallaryImgs
               this.list = data.categoryList
               this.id = data.categoryList.id
           }
        }
    }
}
</script>
<style scoped lang="stylus">
.content{
    height 50rem
}
</style>





