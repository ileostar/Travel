<template>
  <div class="wrapper">
    <swiper :options="swiperOption"
            ref="mySwiper"
            @someSwiperEvent="callback">
      <swiper-slide v-for="item of swiperList"
                    :key="item.id">
        <img class="swiper-img"
             :src="item.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination"
           slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'https://img.zcool.cn/community/014b705b35b3d0a80121b9941c1c0a.jpg@1280w_1l_2o_100sh.jpg'
      }, {
        id: '0002',
        imgUrl: 'https://img.zcool.cn/community/01d75f5b35b3caa80121b994bdb848.jpg@1280w_1l_2o_100sh.jpg'
      }, {
        id: '0003',
        imgUrl: 'https://img.zcool.cn/community/01f01e5b35b3d3a80121b99495b03c.jpg@1280w_1l_2o_100sh.jpg'
      }
      ]
    }
  },
  computed: {
    swiper () {
      return this.$refs.mySwiper.swiper
    }
  },
  mounted () {
    // current swiper instance
    // 然后你就可以使用当前上下文内的swiper对象去做你想做的事了
    console.log('this is current swiper instance object', this.swiper)
    this.swiper.slideTo(3, 1000, false)
  }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active {
  background: #fff !important;
}

.wrapper {
  overflow: hidden;
  width: 100%;
  height: 0;
  padding-bottom: 25%;

  .swiper-img {
    width: 100%;
  }
}
</style>