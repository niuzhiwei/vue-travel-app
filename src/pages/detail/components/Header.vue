<template>
   <div>
    <router-link class="header-abs" tag="div" to="/"
    v-show="showAbs">
        <div class="iconfont header-abs-back">&#xe624;</div>
    </router-link>
    <router-link tag="div" to="/">
    <div class="header-fixed"
     v-show="!showAbs" :style="opacityStyle">
        <div class="iconfont header-fixed-back">&#xe624;</div>
        景点详情
    </div>
    </router-link>
    </div>
</template>
<script>
export default {
    name:'DetailHeader',
    data(){
        return{
            showAbs:true,
            opacityStyle:{
                opacity:0
            }
        }
    },
    methods:{
       handleScroll(){
           const top = document.documentElement.scrollTop
           if(top > 60){
               let opacity = top / 140
               opacity = opacity>1? 1:opacity
               this.opacityStyle = {
                   opacity
               }
               this.showAbs = false
           }else{
               this.showAbs = true
           }
       }
    },
    mounted(){
        window.addEventListener('scroll',this.handleScroll)
    },
    deactivated(){
        window.removeEventListener('scroll',this.handleScroll)
    }
}
</script>

<style scoped lang="stylus">
@import '~styles/varibles.styl'
    .header-abs{
        position absolute
        left .2rem
        top .2rem
        width .8rem
        height .8rem
        line-height .8rem
        border-radius .4rem
        background rgba(0,0,0,0.8)
        text-align center
    }
    .header-abs-back{
        color #fff
        font-size .4rem
    }
    .header-fixed{
        z-index 2
        position fixed
        top 0
        left 0
        right 0
        height .86rem
        line-height .86rem
        text-align center
        color #ffffff
        background $bgColor
        font-size .32rem
    }
    .header-fixed-back{
    position absolute
    top 0
    left 0
    width:.64rem
    text-align center
    color #fff
    font-size .4rem
}
</style>


