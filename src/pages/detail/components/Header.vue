<template>
  <div>
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs"><div class="iconfont header-abs-back">&#xe614;</div></router-link>
    <div class="header-fixed"
        v-show="!showAbs"
        :style="opacityStyle"
        >
      景点详情
      <router-link to="/">
        <div class="iconfont header-fixed-back">&#xe614;</div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop || document.body.scrollTop || window.pageYOffset
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  mounted () {
    window.addEventListener('scroll', this.handleScroll)
  },
  destroyed () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header-abs
    position absolute
    left .2rem
    top .2rem
    width .8rem
    height .8rem
    border-radius: .4rem
    background: rgba(0, 0, 0, .8)
    .header-abs-back
      color: #fff
      text-align: center
      font-size: .4rem
      font-weight: 700
      line-height: .8rem
  .header-fixed
    position: fixed
    top 0
    left 0
    right 0
    z-index: 2
    overflow: hidden
    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    color: #fff
    background: $bgColor
    font-size: 0.32rem
    .header-fixed-back
      position: absolute
      top: 0
      left: 0
      width: 0.64rem
      text-align: center
      font-size: 0.4rem
      color: #fff
</style>