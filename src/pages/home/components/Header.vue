<template>
   <div class="header">
       <div class="title">
           <img class="title-img" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAF4AAAAoCAMAAABAd72AAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAA8UExURUdwTDMzMzU1NTQ0NDQ0NDY2NjQ0NDMzMzQ0NDMzMzMzMzQ0NDQ0ND09PTk5OTQ0NDMzMzMzMzQ0NDMzM192AfkAAAATdFJOUwCuLG6RHmPZv/bnOoAGEFakzUmkBQa7AAACxElEQVRIx5VX2YKDIAysAkK4BPz/f10tCIRrd+elSumQhMnRz9EhsM8KzOYn94WOb3A9gGa3v3psqwMoiCOeQOPuEM+KL77dPaC/pJ3Ti8dGehvAor0uLodkWbPbyhG/m9PH/aDNFh9YDKlL9G+IyQN1GyFG5k/Z7buFxw/CrinkN8j7SSJ0vgiY02NrhFFz+tD8ds+mLe5WCWQfmbLTTnRZO/XirhLeC9fZyTu4mn+RFqpnbj4z63U21ZWr93n/llZIcakyK54Oe+f3+TKdKdBb5SvP2aB4F0JS4kGyYy2y1/HkXXYyeFbdQF8pfY580Dm4tfeH8A0DG7Cbs1YOTrYbqjqnh0fCqSPjWe/PLV9CE9K6S8fIuNoUF6iFUwt6syjE2Qp5reDNQjjFeCAoxJKmjcIu2dvbRcIxMCig4oLtNK8dVP2HHQvndWWr9auDqewgJy/IcYqvnrKlcB4K2MhurGU3RnZU5hmSnJVqWk2QcB6KHJ+SxrWmypmBNxoYwCDhOBRIlOGW47Kaixw/F6UQC8dP24uSqPHtWWIiJAybKa44MCoIiM3hV9RIwi8VBzWh7DOqCXc2qO2vraTk0Vc44UI8kVyjLD2VX2RsR89r4ZCevVxOEo5bJdVaOHlA4aq9HHgnpmI86J1FBNFV05Fw3tKnTXM5/rCQnISLi7ZtfYwfzxpYOPybtIfBWc31nm99Y1t4nTTdYCbWrUqTs2uWJ6v7alVWgWaotESXwlmBNE424yNvwzUQzgq0OGlawRzvUlfZ4BpPocMhNsV779jfJTYbHsVv9FCkkeTgYtwJy0sw1SWoNftZWZHkYDuF+Onoe0dfLOAH/biKRJpe3GRw/zNUdQ3bbiN2ImdzDv0Xu+xGIVRx+qZl+T/Y0wUdk69HQ9rwf8rE9oAKTAs9braBegkAa7ulf0ad3AJ8u527Uk1+ALbVjTqToBHYAAAAAElFTkSuQmCC">
       </div>
       <div class="header-item">
      <div class="header-left">
          <div class="iconfont back-icon">&#xe624;</div>
      </div>
      <div class="header-input">
          <span class="iconfont">&#xe632;</span>
          马来西亚签证
      </div>
      <router-link to="/city">
          <div class="header-right">
           {{this.city}}
          <span class="iconfont arrow-icon">&#xe64a;</span>
         </div>
      </router-link>
      </div>
   </div>
</template>
<script>
import { mapState} from 'vuex'
export default {
    name:'HomeHeader',
    computed:{
        ...mapState(['city'])
    }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
    .header
        background :$bgColor;
    .title
        text-align center
        overflow hidden
    .title-img
        max-width .86rem
        margin-top .2rem
        margin-bottom .1rem
    .header-item
      display:flex
      height :1rem
      line-height:1rem
      color:#fff
    .header-left
        width:0.64rem
        float:left
    .back-icon
       text-align:center
       font-size:.4rem
   .header-input
         flex:1
         line-height :.64rem
         height:.64rem
         margin-top :.12rem
         margin-left:.2rem
         background:#fff
         border-radius:.1rem
         color:#ccc
         padding-left:.2rem
    .header-right
           min-width:1.04rem
           padding .1rem
           padding-top 0
           float:right
           text-align:center
           color:#fff
     .arrow-icon
         margin-left:-.04rem
         font-size:.2rem
     
</style>