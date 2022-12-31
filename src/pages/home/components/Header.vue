<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe614;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe615;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="iconfont arrow-icon">&#xe600;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

// 使用stylus编写样式，使用scoped关键字设置当前样式只对该组件有效（局部化样式）
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
  display: flex
  line-height: $headerHeight
  background-color: $bgColor
  color: #fff
  .header-left
    width: 0.64rem
    float: left
    .back-icon
      text-align: center
      font-size: 0.4rem
  .header-input
    flex: 1
    background: #fff
    height: 0.64rem
    padding-left: 0.2rem
    line-height: 0.64rem
    margin-top: 0.12rem
    margin-left: 0.2rem
    border-radius: 0.1rem
    color: #ccc
  .header-right
    width: 1.24rem
    float: right
    text-align: center
    color: #fff
    .arrow-icon
      font-size: 0.24rem
</style>