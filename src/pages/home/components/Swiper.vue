<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <!-- slides -->
      <swiper-slide v-for="item in list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" alt="">
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
        loop: true
      }
      // swiperList: [{
      //   id: '0001',
      //   imgUrl: 'https://img1.qunarzz.com/piao/fusion/1808/fd/fddc5309111a0402.jpg_750x200_e7b93551.jpg'
      // }, {
      //   id: '0002',
      //   imgUrl: 'http://img1.qunarzz.com/piao/fusion/1808/18/2dbce82b07a23402.jpg_750x200_14356b03.jpg'
      // }]
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
  .wrapper >>> .swiper-pagination-bullet-active
    background-color: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 26.7%
    .swiper-img
      width: 100%
</style>
