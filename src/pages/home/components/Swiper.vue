<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <!-- slides -->
      <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl"/>
      </swiper-slide>
      <!-- Optional controls -->
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
        loop: true
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
  // >>>穿透，就可不受scoped限制，否则scope限制样式只对当前组件生效
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    // 宽高比例设置，不能将height设为32%，因为高度相对的不是宽
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 30.4%
    background-color: #eee
    .swiper-img
      width: 100%
</style>
