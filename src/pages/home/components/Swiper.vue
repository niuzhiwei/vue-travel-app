<template>
    <div class="wrapper">
        <div class="wrapper-swiper">
    <swiper :options="swiperOption" v-if="showSwiper">
    <!-- slides -->
    <swiper-slide v-for="item in list" :key='item.id'>
        <img class="swiper-img" :src="item.imgUrl">
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
  </div>
</template>
<script>
export default {
    name:'HomeSwiper',
    props:{
       list:Array
    },
    data (){
        return{
            swiperOption:{
                pagination:'.swiper-pagination',
                loop:true
            }
        }
    },
    computed:{
        showSwiper(){
            return this.list.length
        }
    }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.wrapper >>> .swiper-pagination-bullet-active
       background:rgb(255,214,43);
.wrapper 
    width:100%;
    background $bgColor
    height 20vw
.wrapper-swiper
    width:95%
    height:350vw
    margin:0 auto;
.swiper-img 
    width:100%
    border-radius .15rem
</style>


