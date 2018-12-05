<template>
    <div>
        <div class="recommend-title">周末去哪儿</div>
        <ul>
            <li class="item border-bottom" v-for="item in list" :key="item.id">
                    <div class="item-img-wrapper">
                    <img class="item-img" :src="item.imgUrl">
                    </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <p class="item-price">￥{{item.price}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    name:'HomeWeekend',
    props:{
        list:Array
    }
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.recommend-title{
    line-height :.8rem;
    background:#eee;
    text-indent:.2rem;
}
.item{
    float left
    max-width 49%
}
.item-img-wrapper{
   overflow hidden
   height 0
   padding-bottom 100%
   margin:.1rem;
   width 100%
}
.item-img{
    max-width 98%
    border-radius .2rem
}
.item-info{
    padding 0.1rem
    min-width 0
}
.item-title{
    color rgb(90,150,145)
    line-height .54rem
    font-size:.32rem
    ellipsis()
}
.item-desc{
    font-weight bold
    line-height .4rem
    color:#000
    ellipsis()
}
.item-price{
    font-size .4rem
    color rgb(255,101,30)
    padding-top .1rem
}
</style>


