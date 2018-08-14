<template>
  <div>
    <div class="banner" @click="handleBannerCLick">
      <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1411/1a/5582f9f24bc50b475a8cbda4c5ac8d24.water.jpg_600x330_e8437d6f.jpg" alt="">
      <div class="banner-info">
        <div class="banner-tittle">秦始皇陵博物院(AAAAA景区)</div>
        <div class="banner-number"><span class="iconfont banner-icon">&#xe692;</span>39</div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary"
      @close="handleGallaryColose"
    ></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'Banner',
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1505/10/100d2e82848fb2.water.jpg_r_800x800_5b03aa73.jpg', 'http://img1.qunarzz.com/sight/p0/1411/6f/9e2a73e12689fc87f27e7f4a252b74b0.water.jpg_r_800x800_9daf6ce2.jpg', '  http://img1.qunarzz.com/sight/p0/1507/1b/4eca8b1c528e259fc69a2119cda278f0.water.jpg_r_800x800_15a9c15b.jpg']
    }
  },
  methods: {
    handleBannerCLick () {
      this.showGallary = true
    },
    handleGallaryColose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-tittle
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        padding: 0 .4rem
        margin-top: .14rem
        height: .4rem
        line-height: .4rem
        border-radius: .2rem
        font-size: .24rem
        background: rgba(0,0,0, .8)
        .banner-icon
          font-size: .24rem
          margin-right: .1rem
</style>
