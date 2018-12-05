<template>
    <div>
        <div class="hot-title">
            <img class="hot-tltle-img" src="http://img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png" alt="">
            本周热门榜单
        </div>
        <div class="hot-item">
            <swiper :options="swiperOption">
                <swiper-slide v-for="(page,index) of pages" :key="index">
                    <div class="hot" v-for="(item) in page" :key="item.id">
                        <div class="hot-img">
                            <img class="hot-img-content" :src="item.imgUrl" alt="">
                        </div>
                        <p class="hot-desc">
                            <span class="hot-rank">{{item.rank}}</span>
                            {{item.desc}}
                        </p>
                        <p class="hot-price">￥
                            <span class="hot-price-much">{{item.price}}</span>起</p>
                    </div>
                </swiper-slide>
            </swiper>
        </div>
    </div>
</template>
<script>
export default {
  name: 'HomeHot',
  props: {
    list: Array
  },
  data() {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    pages() {
      var pages = []
      this.list.forEach((item, index) => {
        var page = Math.floor(index / 4)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>
<style scoped lang="stylus">
@import '~styles/varibles.styl';
@import '~styles/mixins.styl';

.hot-title {
    margin-top: 0.2rem;
    line-height: 0.8rem;
    background: #eee;
    text-indent: 0.2rem;
}
.hot-tltle-img{
    width 7%
}

.hot-item {
    overflow: hidden;
    position: relative;
}

.hot {
    overflow: hidden;
    float: left;
    width: 22.8vw;
    height: 0;
    padding-bottom: 33.6%;
    position: relative;
    margin: 1vw;
}

.hot-img-content {
    width: 100%;
    height: 100%;
}

.hot-desc {
    margin-top: 0.1rem;
    font-size: 0.24rem;
    text-align: center;
    ellipsis();
}

.hot-price {
    margin-top: 0.1rem;
    font-size: 0.24rem;
    text-align: center;
}

.hot-price-much {
    font-size: 0.28rem;
    color: rgb(255, 134, 7);
}
.hot-rank{
    color red;
    font-size .26rem
}
</style>

