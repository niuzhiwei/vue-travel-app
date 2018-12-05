<template>
    <div>
        <div class="item" v-for="(item,index) in list" :key="index">
            <div class="item-title border-bottom">
                <span class="item-title-icon"></span>
                {{item.title}}
                <div class="item-price">{{item.price}}</div>
                <div class="item-children"> {{item.children.title}}</div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name:'DetailList',
    props:{
        list:Array
    }
}
</script>
<style scoped lang="stylus">
.item-title{
   line-height .8rem
   font size 0.32rem
   padding: 0 .2rem
}
.item-title-icon{
    position relative
    left .06rem
    top .06rem
    display: inline-block
    width: .36rem;
    height: .36rem;
    background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
    margin-right: .1rem;
    background-size: .4rem 3rem;
}
.item-children{
   padding 0 .2rem
   font-size .25rem
   color gray
}
.item-price{
    float right 
    color rgb(255,153,24)
}
</style>


