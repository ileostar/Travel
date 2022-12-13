<template>
<div class="header">
    <div class="header-left">
        <div class="iconfont back-icon">&#xe614;</div>
    </div>
    <div class="header-input">
        <span class="iconfont">&#xe615;</span>
        输入城市/景点/游玩主题
    </div>
    <div class="header-right">
        城市
        <span class="iconfont arrow-icon">&#xe600;</span>
    </div>
</div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

// 使用stylus编写样式，使用scoped关键字设置当前样式只对该组件有效（局部化样式）
<style lang="stylus" scoped>
 @import '~styles/varibles.styl';
 .header
  display: flex
  line-height: .86rem
  background-color: $bgColor
  color: #fff
  .header-left
    width: .64rem
    float: left
    .back-icon
     text-align: center
     font-size: .4rem
  .header-input
    flex: 1
    background: #fff
    height: .64rem
    padding-left: .2rem
    line-height: .64rem
    margin-top: .12rem
    margin-left: .2rem
    border-radius: .1rem
    color: #ccc
  .header-right
    width: 1.24rem
    float: right
    text-align: center
    .arrow-icon
     font-size: .24rem
</style>