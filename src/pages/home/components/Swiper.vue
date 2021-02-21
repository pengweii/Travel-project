<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
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
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'https://imgs.qunarzz.com/vs_ceph_vcimg/f7813c9431796cc32ae7b7a78447342e.jpeg'
      }, {
        id: '0002',
        imgUrl: 'https://imgs.qunarzz.com/vs_ceph_vcimg/569cae4ae98e9793f7341e85eed73c54.jpeg'
      }, {
        id: '0003',
        imgUrl: 'https://imgs.qunarzz.com/vs_ceph_vcimg/f03f5ac90ae59d0d9c6332a2bfd9782e.jpeg'
      }]
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
