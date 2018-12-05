<template>
    <div>
        <div class="recommend-title">
            <img class="recommend-title-img" src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="">
            猜你喜欢
        </div>
        <ul>
            <router-link :to="'/detail/' + item.id"
             class="item border-bottom" v-for="item in list" :key="item.id" tag="li">
                    <img class="item-img" :src="item.imgUrl">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </router-link>
        </ul>
    </div>
</template>
<script>
export default {
    name:'HomeRecommend',
    props:{
       list:Array
    }
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.recommend-title{
    margin-top :.2rem;
    line-height :.8rem;
    background:#eee;
    text-indent:.2rem;
}
.recommend-title-img{
   width 7%;
}
.item{
    overflow hidden
    display:flex;
    height:1.9rem;
}
.item-img{
    width:1.7rem
    height 1.7rem
    padding .1rem
}
.item-info{
    flex:1
    padding 0.1rem
    min-width 0
}
.item-title{
    line-height .54rem
    font-size:.32rem
    ellipsis()
}
.item-desc{
    line-height .4rem
    color:rgb(255,85,85)
    ellipsis()
    font-size .23rem
}
.item-button{
    line-height .44rem
    margin-top .3rem
    background-color rgb(0,188,212)
    padding 0 .2rem
    border-radius .06rem
    color #fff
}
</style>


