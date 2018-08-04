<template>
  <div class="wrapper">
    <!-- v-if="list.length" 刚开始 -->
    <swiper :options="swiperOption" v-if="showSwiper">
      <swiper-slide v-for="item of list" :key="item.id"  data-swiper-autoplay="2000">
        <img class="swiper-img" :src="item.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: true,
        loop: true
      }
    }
  },
  computed: {
    showSwiper () {
      /* 避免模版中出现逻辑代码 所以使用计算属性来处理  swiper第一次创建是由空数组创建的，数据出现后又再一次创建，所以刚开始展示的是第四个页面,所以,只要第一次创建通过完整的数据创建就正常了 */
      return this.list.length
    }
  },
  methods: {
    callback () {

    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 26.6%
    background: #eee
    .swiper-img
      width: 100%
</style>
